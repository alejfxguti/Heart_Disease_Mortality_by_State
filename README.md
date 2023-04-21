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

## Installations/Prerequisites for choropleth maps: 
    - plotly
    - plotly_express
    - plotly chart_studio
    - geopandas
    - fiona
    - folium

## Reference guides used: 

    - plotly
       - https://plotly.com/python/getting-started/
       - https://towardsdatascience.com/geographical-plotting-of-maps-with-plotly-4b5a5c95f02a
       - https://plotly.com/python/choropleth-maps/
       
    - folium 
       - https://towardsdatascience.com/folium-and-choropleth-map-from-zero-to-pro-6127f9e68564
       - https://towardsdatascience.com/folium-mapping-displaying-markers-on-a-map-6bd56f3e3420
       - https://www.analyticsvidhya.com/blog/2020/06/guide-geospatial-analysis-folium-python/
       - https://github.com/python-visualization/folium/issues/403 --> choosing color schemes
       - https://github.com/python-visualization/folium/issues/1202 --> adding titles to maps
       - https://getbootstrap.com/docs/3.3/components/#glyphicons-glyphs --> icon set options

## Instructions to open the html image files - 
       - 1) Click on the html file 
       - 2) View Raw -> opens HTML code 
       - 3) Right click on the code 
       - 4) Save as HTML file in your local
       - 5) Open to view as HTML

## Research Questions
- Is there a relationship between health spending per capita and heart disease mortality rates? 
- Is there a relationship between health Insurance coverage and heart disease mortality rates?
- Do states with higher healthcare spending per capita have higher rates of health insurance coverage?
- Is there a relationship between a state’s location and its heart disease mortality rate?

## Analysis
### Is there a relationship between health spending per capita and heart disease mortality rates? 

The bar chart shows the deaths rates per 100k by state from Highest to Lowest: 

![image](https://user-images.githubusercontent.com/126313924/233537324-b228c34a-5598-4345-ae91-3a7bc7e804cd.png)

Map shows the distribution of Average Healthcare spending by State from Highest to Lowest spending states by color: 

![image](https://user-images.githubusercontent.com/126313924/233537605-833327c6-9605-4639-a69e-6590858de9ed.png)

We can see that - Utah, Texas, Idaho, Arizona, Nevada being states which tends to spend less towards healthcare services, this helps us to do our analysis of the first 
question. 

We wanted to investigate whether the amount a state pays per person on health care services impacts heart disease mortality rates. We hypothesized that states who spend more per person would likely have lower heart disease mortality rates.

Scatter plot was used to determine the correlation and its linearity, followed by the geographical visualization. 

Scatter plot: 
- Spending vs Mortality
![SpendingVsMortality](output_fig/LRSpendingVsMortality.png)

- The rvalue is -0.2378, indicating a weak negative correlation between health spending per capita and heart disease mortality rate.
- The r-squared value is 0.0566, indicating that only 5.7% of the variation in heart disease mortality rate can be explained by health spending per capita.
- The p-value is 0.0963, which is not statistically significant at the standard 0.05 level, suggesting that there is not strong enough evidence to say that there is a significant relationship between health spending per capita and heart disease mortality rate.
- The standard deviation of 0.0028 suggests that the regression line is a relatively decent fit for the data, as the distance between the actual data points and the predicted values is relatively small. 

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

     - The Linear Regression Statistics between Mortality & Insured per state has weak NEGATIVE correlation coefficient "r-value" -0.31 
     - The 0.094 is a small r-squared value means 9.4% of Mortality (Death) has dependency on Insurance coverage & that’s a WEAK direct impact relationship.
     - The "p-value" 0.031 is lower than the significance level (P ≤ 0.05) means that the test hypothesis is false or should be rejected.
     - 1.29 Std. Dev shows that the data points spread around the regression line values are generally far & scattered from the mean
     - Graph is a good proof that the more insured citizens the less heart disease mortality but with a very weak impact.


- Uninsured vs Mortality
![LRUninsuredVsMortality](https://user-images.githubusercontent.com/123844669/233252205-aeeb1599-282c-431a-b9be-a9b1860c202d.png)

     - The Linear Regression Statistics between Mortality & Uninsured per state has weak POSITIVE correlation coefficient "r-value" +0.31 
     - The 0.094 is a small r-squared value means 9.4% of Mortality (Death) has dependency on Insurance coverage & that’s a WEAK direct impact relationship.
     - The "p-value" 0.031 is lower than the significance level (P ≤ 0.05) means that the test hypothesis is false or should be rejected.
     - 1.29 Std. Dev shows that the data points spread around the regression line values are generally far & scattered from the mean.
     - Graph is a good proof that the more uninsured citizens the less heart disease mortality but with a very weak impact.


Map visualization: 

In support of the linear regression analysis in scatter plots, this map acts like a visual journey to establish the correlation of Mortality rate with uninsured percentage. By identifying the states having Highest(Top 5) Deaths per 100k and Lowest(Bottom 5) Deaths per 100k we plotted them over the distribution of % uninsured by State in Choropleth map. Blue and Red indicating the Lowest and Highest Deaths per 100k respectively. It somewhat appears that states having the most uninsured population have higher mortality rates than states having the most insured population. However, if there was a strong correlation between heart mortality rate and % uninsured, then we would have seen Texas to be having the Highest deaths per 100k, Texas displaying the highest % uninsured.This tells us there could be other factors that could account for this outcome which were not considered in this analysis. 

![image](https://user-images.githubusercontent.com/126313924/233284594-d047776b-19ee-4374-a0e3-6526fb68ad9a.png)
![image](https://user-images.githubusercontent.com/126313924/233284712-64f5870d-c120-4b9c-82cc-b90eb5ab1a68.png)


### Do states with higher healthcare spending per capita have higher rates of health insurance coverage?
This scatter plot shows the correlation between healthcare spending vs health insurance coverage. Different types of health coverage is identified across all the states in the US during 2019. The types of health coverage includes employer, non-group, Medicaid, Medicare, and Military. States with higher healthcare spending tend to have a greater percentage of insured coverage.

The r-value 0.52 identifies moderate correlation. The r-squared value of 0.27 is fairly low and does no explain the variation in the data much. The low p-value is statistically significant and most likely the null hypothesis is rejected. The low standard deviation indicates that the data is close to the mean.


![Unknown](https://user-images.githubusercontent.com/125218833/233448394-0e43e4b4-f0af-4d3b-8e7c-9d261de76762.png)







### Is there a relationship between a state’s location and its heart disease mortality rate?
This scatter plot visualizes a state's latitude vs. its death rate per 100,000 people:

![lat_vs_rate](https://user-images.githubusercontent.com/123991074/233485308-d2787197-289b-42e2-8d53-aa23eec9c042.png)

The r-value is: -0.337 \
The r-squared is: 0.114 \
The p-value is: 0.016 \
The Std. Dev. is: 0.680

The linear regression for Latitude vs Death Rate per State shows a negative correlation, meaning that as a state's latitude increases, their death rate decreases. The r-value of -0.337 indicates a fairly weak negative correlation between latitude and death rate per state. The r-squared value of 0.114 indicates that 91% of the variability in the outcome is due to factors not accounted for in the model. Additionally, the standard deviation of 0.680 is quite low, indicating that there is low variance in the data and the values are all very close to the mean. The p-value is quite strong at roughly 0.02, indicating very high accuracy of these findings.

This scatter plot visualizes a state's latitude vs. its death rate per 100,000 people:

![lon_vs_rate](https://user-images.githubusercontent.com/123991074/233485479-6d58a6fc-8188-4c87-ab84-a445bee3872b.png)

The r-value is: 0.263 \
The r-squared is: 0.069 \
The p-value is: 0.065 \
The Std. Dev. is: 0.214

The linear regression for Longitude vs Death Rate per State shows a positive correlation, meaning that as a state's longitude increases, so does its death rate. The r-value shows a weak correlation between state longitude and death rate at 0.263. The r-sqared value is roughly 0.07, indicating that 93% of the variability in the outcome is due to factors not accounted for in the model. The standard deviation of 0.214 is quite low, indicating that there is low variance in the data and the values are all very close to the mean. The p-value is fairly average at roughly 0.06, meaning that these findings are likely accurate.

It is unlikely that the latitude or longitude of a state has much of an impact on the state's heart disease mortality rate, but there is some correlation. Based on these findings, it is very likely that the outcome is the result of other factors not accounted for in our analysis.


