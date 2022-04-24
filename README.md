# SC1015_Project_Data_science

## About 

## Problem Definition

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


## Contributors
- @PRATEEKA001 - Data collection & preparation
- @keyqq117 - Data analysis & visualization
- @syed0059 - machine learning model(SVR) & insights

## Models Used

## Conclusion

## References
