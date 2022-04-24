# SC1015_Project_Data_science

## Contributors
- @PRATEEKA001 - Data collection & preparation
- @keyqq117 - Data analysis & visualization
- @syed0059 - machine learning model(SVR) & insights

## About 

### Problem Definition
People all over the world are experiencing great difficulties, especially due to Covid-19 pandemic that still claims lives and disrupts economies. The world happiness report indicates that worry and stress levels have risen by 4% since 2021. We found it interesting that the happiness report was so reflective of real-world events, and wanted to explore this report further.
We wanted to find out what contributed to happiness. Why do some countries have a high happiness score year after year, while others remain at the bottom of the happiness ranking?
This led to our problem statement: **How can we determine the most important factors affecting a country’s Happiness Score?**

### Data Preparation
The first step in our journey for an answer involved cleaning and preparing the data.
From the core Happiness Report dataset, we focused on significant variables that appeared in each year’s datasets. These include Happiness Score, Gross Domestic Product, and the factors of Healthy Life expectancy, Social support, freedom to make life choices, etc.

There were many differences between the datasets of different years, such as different variable names and varying organisation of data. As such, the datasets from different years first needed to be standardised. So, we ensured that column headings for the datasets were the same across all years, by individually renaming the column headings.Not all countries were represented in every year's survey, so we used 2015 as the base and filtered the other years to only include those countries.
Afterwards, it was important to change data type for the variables from object to float64, to allow for data analysis.
We further had to merge some of the datasets to produce the regional indicator column. For some of the years like the 2018 dataset, the residual had to be derived by subtracting the factors from the happiness score.

Thus, we produced cleaned versions of each year's dataset.

### Exploratory Data Analysis
During the exploratory data analysis process, we wanted to find out which of the variables were more important in influencing the happiness score. 

With region being a categorical data, we chose to use a boxplot analysis on each of the different region. From the boxplot visualisation, we can see that there are clear differences in happiness score between the different regions,  this suggest that region could be an important factor in determining the happiness score of a country. What we found was that the happiest region was the Australia and New Zealand region. The Australia and New Zealand region has two countries, which both ranked very highly on the happiness score. Another noteworthy finding is that the region containing the happiest country is not the happiest region, this suggest that region alone cannot explain for the difference in happiness score between countries. 

To further investigate the other numerical data variables, we used a correlation analysis through the use of a correlation matrix to visualise the correlation between each variable and happiness score across the years and also the combined dataset of all the years. 
What we found was that for most years, GDP had the highest correlation with happiness score. Thus, we find that gdp does have the highest correlation with happiness score compared to the other variables.

To better illustrate the correlation between GDP, region and happiness score, we use a regression analysis. We first plotted a scatter point of the data sets, using different colours to represent different regions, we then plotted a regression line for each of the region, as well as a overall regression line of all the points. Most regions had a positive correlation between GDP and happiness. From our linear regression analysis we can clearly see a strong correlation between a country’s happiness score and both its region and gdp variables. As such, we tried to see if we could do more with this two variables. 


### Machine Learning Model
To build on top of our initial problem, we decided to use machine learning to see if happiness could be estimated using the region and GDP per capita. GDP per capita is the factor that is most highly correlated with happiness, and we see from the previous graphs that ‘region’ is also very highly correlated with happiness as well.Estimating the happiness score with only 2 variables would allow us to further prove the significance of such variables in the happiness of a country’s population; and given the region and GDP per capita of an unknown country, we could estimate the happiness score of its population.

For our estimations, we decided to learn about and implement SVR, support vector regression. SVR is an extension of SVM where the model tries to create the best fitting hyperplane as well as an upper and lower boundary called the margin. The model tries to fit as much of the given data within the margin, while also trying to minimise the deviation of points outside of the margins. 

SVR chooses the hyperplane using kernels, which are functions that map given data to higher dimensions to make it easier to separate them. For the kernel, we tested a linear kernel, a polynomial kernel, and the radial basis function kernel. We also compared our results from the SVR models against an ordinary least squares linear regression model to see how well SVR does. After fitting and testing the 3 SVR models and the linear regression model, we see that although all three of them achieved somewhat similar R^2 scores in the train sets, SVR with the RBF kernel achieved the highest scores across both the train and test sets.

However, we noticed a lot of variation in the scores for every train-test split we conducted. This is because the sample size of each set is relatively very small and so there is a lot of variability in the data every time it is split. To combat this, we also used K-Folds cross validation with k = 10, to reduce the variability and increase consistency in the results.

After this, we achieved much more consistent results, as seen on the table. SVR still outperforms OLS across the board in the test sets, with the RBF version getting the highest R2 scores in both train and test sets.

### Model Efficacy
From the above results, we see that our accuracy is consistently relatively high. This shows that the region of a country is a relatively significant factor in the determination of a population’s happiness. This is possibly because the region a country belongs to is a broad indicator of many other factors that influence happiness, such as freedom as well as many other intangible factors that cannot be measured.
Overall, our model shows a high degree of correlation between region, gdp, and happiness, however, our results are inherently limited as there are only so many countries in the world. All of our models had very similar accuracies to each other, but the highest of them was SVR with RBF kernel as it allowed for better separation of the points using the kernel to choose the best hyperplane. SVR provided more accurate results over simple OLS in most cases, combining it with K-folds made the results more consistent and reproducible while also improving the score in the test cases.


## Conclusion
In conclusion, we have identified the variables that are most highly correlated with happiness which are gdp per capita, social support, and healthy life expectancy. We have also found that although region is not accounted for in happiness score, it is a relatively reliable indicator of happiness as well. This might explain the increase in worry and stress mentioned earlier, as many of the factors strongly associated with happiness have declined due to Covid. 



## References
Kaggle - https://www.kaggle.com/datasets/mathurinache/world-happiness-report?resource=download&select=2022.csv
