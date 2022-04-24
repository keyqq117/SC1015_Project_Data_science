# SC1015_Project_Data_science

## About 

# Data Preparation
The first step in our journey for an answer involved cleaning and preparing the data.
From the core Happiness Report dataset, we focused on significant variables that appeared in each year’s datasets. These include Happiness Score, Gross Domestic Product, and the factors of Healthy Life expectancy, Social support, freedom to make life choices, etc.
The happiness score is based on answers to life evaluation questions inquired within the Gallup World Survey. It is the sum of all factors plus the residual sum, and serves as a broad comparative indicator for happiness levels in a country.
There were many differences between the datasets of different years, such as different variable names and varying organisation of data. As such, a considerable amount of data preparation was needed.

The datasets from different years first needed to be standardised. So, we ensured that column headings for the datasets were the same across all years, by individually renaming the column headings.
Not all countries were represented in every year's survey, so we used 2015 as the base and filtered the other years to only include those countries.
Afterwards, it was important to change data type for the variables from object to float64, to allow for data analysis later on.
We further had to merge some of the datasets to produce the regional indicator column, and for some of the years like the 2018 dataset, the residual had to be derived by subtracting the factors from the happiness score.


## Contributors
- @PRATEEKA001 Data collection & preparation
- @keyqq117 Data analysis & visualization
- @syed0059 machine learning model(SVR) & insights
