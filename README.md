# Heart Disease Mortality by State
What factors – if any – contribute to disparities in rates of heart disease mortality between U.S. states?

## Contributors
- Hany Dief -- (@hanydief)
- Katie Djahan -- (@katiedjahan)
- Alejandro Gutierrez -- (@alejfxguti)
- Bijoyeta Kayal -- (@BijoyetaK)
- Tristan Marcum -- (@TinTesla)
- Niti Patel -- (@niti2442)

## Google Slides Presentation Link
- https://docs.google.com/presentation/d/1RItzAx6IIT7TmEUKtCG-CGicsitFdo_TUHq8sZhzmts/edit?usp=sharing

## Problem Overview
Heart Disease Mortality is a serious public health issue and one of the leading causes of death in the US. Understanding the factors that are associated with heart disease mortality is crucial in identifying potential solutions to this problem.

We analyzed various data sources to determine whether insurance coverage, healthcare spending, or geographic location have an impact on the rate of heart disease mortality at the state level.

## Data Sources
- [Rates of Healthcare Coverage by State (2019)](https://www.kff.org/other/state-indicator/total-population/?currentTimeframe=1&sortModel=%7B%22colId%22:%22Location%22,%22sort%22:%22asc%22%7D)
- A breakdown of the percentage of insured and uninsured people in each state in 2019
- [Health Care Expenditures per Capita by State of Residence (2019)](https://www.kff.org/other/state-indicator/health-spending-per-capita/?currentTimeframe=1&sortModel=%7B%22colId%22:%22Location%22,%22sort%22:%22asc%22%7D)
    - Amount that each spends on healthcare per capita in 2019
- [Heart disease mortality by state (use 2019 data)](https://www.cdc.gov/nchs/pressroom/sosmap/heart_disease_mortality/heart_disease.htm)
    - Heart disease mortality data by state – total heart disease deaths and deaths per 100k
- [US states coordinates](https://developers.google.com/public-data/docs/canonical/states_csv)
    - Latitude and longitude coordinates for each state
- [Geojson file for state geometry data in Maps](https://eric.clst.org/tech/usgeojson/)
    - Json format file having geometry information that defines the boundaries of each area in the map
    - GeoJSON file has an ID field or some identifying value in properties which is used as a key to match the values of locations/state codes included our dataframes.
- We did not use the individual breakdowns of the types of insurance in the first dataframe

## Research Questions
- Is there a relationship between health spending per capita and heart disease mortality rates? 
- Is there a relationship between health Insurance coverage and heart disease mortality rates?
- Do states with higher healthcare spending per capita have higher rates of health insurance coverage?
- Is there a relationship between a state’s location and its heart disease mortality rate?

## Analysis
### Is there a relationship between health spending per capita and heart disease mortality rates? 
Map visualization: 

In support of the linear regression analysis in scatter plots, this map acts like a visual journey to establish the correlation of Heart disease Mortality rate 
with Health Spending per capita. By identifying the states having the Highest(Top 5) Deaths per 100k and Lowest(Bottom 5) Deaths per 100k we plotted them over the
distribution of Average Health Spending per capita by State in a Choropleth map. Blue and Red indicating the Lowest and Highest Deaths per 100k respectively. 

It somewhat appears that state spending the most in Healthcare have lower Mortality rates than states spending the least on Healthcare. 
However, if there was a strong correlation between heart mortality rate and health spending by state, then we would have seen Texas, Nevada, Idaho, Utah, Arizona,
indicating highest deaths per 100k. This tells us there could be other factors that could account for this outcome which were not considered in this analysis. 

![image](https://user-images.githubusercontent.com/126313924/233286266-1fe59473-f11e-4277-9f19-791ee0626ed2.png)
![image](https://user-images.githubusercontent.com/126313924/233286364-fc5c93a0-e071-41dd-b9da-802d358446f5.png)


### Is there a relationship between health Insurance coverage and heart disease mortality rates?
By replying to this question we are trying to identify if heart disease mortality has any correlation with insurance coverage or if insurance coverage has any impact on reducing the heart disease mortality within the United States.

Scatter plots were used to determine the correlation and its linearity, followed by the geographical visualization. 

Scatter plots: 
- Insured vs Mortality
![LRInsuredVsMortality](https://user-images.githubusercontent.com/123844669/233252181-ca03a2e7-c4e1-4012-a9f1-5c6689a47b93.png)

The Linear Regression Statistics between Mortality & Insured per state has negative correlation with "r-value" -0.31 & r-squared 0.094 means 9.4% of Mortality (Death) has direct impact relationship from Insured citizens.
"p-value" is 0.031 & the same with Std. Dev is almost 1.29 & that represents a negative correlation with scattered Standard Deviations. 
Graph is a good proof that the more insured citizens the less heart disease mortality but doesn’t have high impact.

- Uninsured vs Mortality
![LRUninsuredVsMortality](https://user-images.githubusercontent.com/123844669/233252205-aeeb1599-282c-431a-b9be-a9b1860c202d.png)

The Linear Regression Statistics between Mortality & Uninsured per state has a positive correlation with "r-value" 0.31 & r-squared 0.094 means 9.4% of Mortality (Death) has direct proportional relationship with Uninsured citizens.
p-value is 0.031 & the same with Std. Dev represents a positive correlation with scattered Standard Deviations not close to the linear regression line Std. Dev. 1.29 .
And graph is a good proof that the more uninsured citizens the more heart disease mortality but doesn’t have high impact.

Map visualization: 

In support of the linear regression analysis in scatter plots, this map acts like a visual journey to establish the correlation of Mortality rate with uninsured percentage. By identifying the states having Highest(Top 5) Deaths per 100k and Lowest(Bottom 5) Deaths per 100k we plotted them over the distribution of % uninsured by State in Choropleth map. Blue and Red indicating the Lowest and Highest Deaths per 100k respectively. It somewhat appears that states having the most uninsured population have higher mortality rates than states having the most insured population. However, if there was a strong correlation between heart mortality rate and % uninsured, then we would have seen Texas to be having the Highest deaths per 100k, Texas displaying the highest % uninsured.This tells us there could be other factors that could account for this outcome which were not considered in this analysis. 

![image](https://user-images.githubusercontent.com/126313924/233284594-d047776b-19ee-4374-a0e3-6526fb68ad9a.png)
![image](https://user-images.githubusercontent.com/126313924/233284712-64f5870d-c120-4b9c-82cc-b90eb5ab1a68.png)


### Do states with higher healthcare spending per capita have higher rates of health insurance coverage?
This scatter plot shows the correlation between healthcare spending vs health insurance coverage. Different types of health coverage is identified across all the states in the US during 2019. The types of health coverage includes employer, non-group, Medicaid, Medicare, and Military. States with higher healthcare spending tend to have a greater percentage of insured coverage.

The r-value 0.52 identifies moderate correlation. The r-squared value is fairly low and does no explain the variation in the data much. The low p-value is statistically significant and most likely the null hypothesis is rejected. The low standard deviation indicates that the data is close to the mean.


![Unknown](https://user-images.githubusercontent.com/125218833/233448394-0e43e4b4-f0af-4d3b-8e7c-9d261de76762.png)







### Is there a relationship between a state’s location and its heart disease mortality rate?

