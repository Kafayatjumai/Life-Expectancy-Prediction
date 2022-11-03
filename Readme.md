# OHT Ibadan BOOTCAMP CAPSTONE PROJECT

## Life Expectancy Prediction

### Kafayat Saka

### Kaggle competition - Link to fianl Leaderboard https://www.kaggle.com/competitions/oht-ibadan-bootcamp-capstone/leaderboard
**Overview**

The project relies on accuracy of data. The Global Health Observatory (GHO) data repository under World Health Organization (WHO) keeps track of the health status as well as many other related factors for all countries The datasets are made available to public for the purpose of health data analysis. The dataset related to **life expectancy**, health factors for 193 countries has been collected from the same WHO data repository website and its corresponding economic data was collected from United Nation website. Among all categories of health-related factors only those critical factors were chosen which are more representative.

Life expectancy is the key metric for assessing population health. it captures the mortality along the entire life course and tells us about the average age of death in a population.

**Objective**

I am required to help save lives, by building a model that helps in predicting "Life expectancy" based on supplied variables. Which will be evaluated with the Root Mean Squared error (RMSE).

**Acknowledgements**

The data was collected from WHO and United Nations website with the help of Deeksha Russell and Duan Wang.

### Variable Descriptions

Format: variable (type) - description

- Year (Ordinal) - the calendar year the indicators are from (ranging from 2000 to 2015)

- Status (Nominal) - whether a country is considered to be 'Developing' or 'Developed' by WHO standards

- Life_expectancy (Ratio) - the life expectancy of people in years for a particular country and year

- Adult_mortality (Ratio) - the adult mortality rate per 1000 population (i.e. number of people dying between 15 and 60 years per 1000 population); if the rate is 263 then that means 263 people will die out of 1000 between the ages of 15 and 60; another way to think of this is that the chance an individual will die between 15 and 60 is 26.3%

- Infant_deaths (Ratio) - number of infant deaths per 1000 population; similar to above, but for infants

- Alcohol (Ratio) - a country's alcohol consumption rate measured as liters of pure alcohol consumption per capita

- Percentage_expenditure (Ratio) - expenditure on health as a percentage of Gross Domestic Product (gdp)

- Hepatitis_b (Ratio) - number of 1 year olds with Hepatitis B immunization over all 1 year olds in population

- Measles (Ratio) - number of reported Measles cases per 1000 population

- Bmi (Interval/Ordinal) - average Body Mass Index (BMI) of a country's total population

- Under-five_deaths (Ratio) - number of people under the age of five deaths per 1000 population

- Polio (Ratio) - number of 1 year olds with Polio immunization over the number of all 1 year olds in population

- Total_expenditure (Ratio) - government expenditure on health as a percentage of total government expenditure

- Diphtheria (Ratio) - Diphtheria tetanus toxoid and pertussis (DTP3) immunization rate of 1 year olds

- Hiv/aids (Ratio) - deaths per 1000 live births caused by HIV/AIDS for people under 5; number of people under 5 who die due to HIV/AIDS per 1000 births

- Gdp (Ratio) - Gross Domestic Product per capita

- Population (Ratio) - population of a country

- Thinness_1-19_years (Ratio) - rate of thinness among people aged 10-19 (Note: variable should be renamed to thinness_10-19_years to more accurately represent the variable)

- Thinness_5-9_years (Ratio) - rate of thinness among people aged 5-9

- Income_composition_of_resources (Ratio) - Human Development Index in terms of income composition of resources (index ranging from 0 to 1)

- Schooling (Ratio) - average number of years of schooling of a population


## Preliminary Wrangling
 
The Training and testing datasets were provided by the Bootcamp.

-1 The train dataset columns were renamed to proper naming conventions.

-2 Status categorical column was converted to integer and values replaced with 0 and 1.

-3 Univariate plot of all variables were plotted where the following findings were recorded:

- 2015 had the highest number of distribution.

- Most of the the distribution for status column fell into 'Developing'

- The life expectancy in which majority of the population fell into is about age 75.

- Adult mortality, infant deaths,alcohol and percentage expenditures are Right skewed distributions.

- Hepatitis B, Polio,Diphtheria follow a Left-skewed distribution.

- BMI follows a Bimodal distribution.

- Total expenditure, Income composition of resources,Schooling have unimodal distribution.

- The rest of the variables follow a Right Skewed distribution.

-4 The correlation between the variables of the dataset and the target variable, life expectancy, was done and the following were observed:

- Adult mortality is negatively correlated with life expectancy.

- Alcohol,GDP and  percentage expenditure is fairly correlated too.

- Bmi with polio and diphteria is fairly correlated.

- Income composition of resources and Schooling is highly correlated.

- The other fairly negative correlations are the HIV/AIDS,thinness  1-19 years and thinness 5-9 years.

- The poorly correlated variables are the ID, Year,infant deaths,Hepatitis B,Measles,under-five deaths,Total expenditure and Population.

-5 Bivariate analysis of the dataset,the following were confirmed by plotting.

- Life expectancy and Schooling are highly correlated. That is an increase in average number of years of schooling of the population results in an increase in life expectancy

- Life expectancy and income composition of resources is also highly correlated. This means populations with an increase income composition of resources have an increased life expectancy.

- Life expectancy and Adult mortality is negatively correlated.Increase in adult mortality leads to a decrease in life expectancy which is understandable.

- Life expectancy and HIV/AIDS. Although a lot of outliers were observed after plotting but generally an increase in deaths caused by hiv/aids by 1000 live birth population led to a decrease in life expectancy for that population.
 
- Status and Life expectancy, the population that comes from developed countries have a higher life expectancy than those that come from developing countries. In which the life expectancy of those from a developing country is 40, and below for the outliers.

## Model 
This dataset contains a lot of Outliers and Missing values. The objective of this project is to build a machine learning model and handling these issues is very sensitive to the performance of the model. I will be dealing with them in the model building phase in another notebook.

The model building phase is in the model building notebook.

Summary:
After an iterative process.
The following were carried out to achieve the model with the lowest RMSE:

- MIssing rows were dropped.
- The year column was dropped.
- Best performing model was Gradient boosting.
- Performed Hyperparameter tuning.

The final model with the best performance using the RMSE as evaluation that was chosen is in the model Folder.


## Conclusion

Although the objective of this project was to build a model. During the exploratory data analysis I discovered the major variables that affected the life expectancy either positively or negatively.
