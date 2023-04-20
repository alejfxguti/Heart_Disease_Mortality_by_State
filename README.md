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


### Is there a relationship between health Insurance coverage and heart disease mortality rates?


### Do states with higher healthcare spending per capita have higher rates of health insurance coverage?


### Is there a relationship between a state’s location and its heart disease mortality rate?

