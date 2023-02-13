# Evaluating the Effects of Air Quality on Health Outcomes Amongst CA Counties
---

# Problem Statement

Pollution has long been known to have a causal effect on negative health outcomes. Our group's goal was to use various statistical hypothesis tests as well as exploratory data analysis and regression analysis to gain a stronger quantitative understanding of the effects of air pollution amongst the 58 counties of California. 

# Background

### EPA Air Quality Data 

Our primary data source and point of departure for all subsequent analysis is EPA air quality data. The EPA monitors and collects data on air pollution in every major city in United States. The air quality data is aggregated in varying levels of granularity. From this collection process, the EPA calculates the Air Quality Index, a measurement of overall danger to health that ranges from 0 (none) to 500 (maximum danger) The AQI is calculated by taking the highest average measurement of each of the constituent pollution factors being monitored, and weighs it by known health effects. 

At the more coarse annual level, we find our chosen dataset: the aggregate level of monitored pollutants, per day, for each County in the United States. 

We collected and cleaned this data from the EPA's website [[SOURCE](https://aqs.epa.gov/aqsweb/airdata/download_files.html#Annual)]. The major air quality metrics monitored are:

1. Days NO2 - Nitrogen Dioxide, very similar to Nitrogen Oxide (NOx). The primary source of atmospheric nitrogen dioxide is the burning of fossil fuels. 

2. Days Ozone - While stratospheric ozone is known to be a good thing due to its blocking of harmful ultraviolet radiation, ground-level ozone has been found to cause a number of health problems. 

3. Days PM2.5 - Fine particulate matter with a diameter 2.5 micrometers or smaller. This matter often emanates from dust stirred up from a construction site or field, or incomplete combustion (smoke) from smoke stacks or a forest fire. PM 2.5 particulate matter is often associated with haze, and, when inhaled, embeds deep in the lungs. 

4. Days PM10 - Coarse particulate matter. Also emanating from dust producing sources as well as incomplete combustion (smoke).

5. Days CO - Carbon Monoxide. Produced by the combustion of fossil fuels and causes a number of lung ailments from fatigue through death.

Exposure to these particulates has been found to lead to negative cardiovascular, respiratory health outcomes as well as increased incidence rates of various cancers. 

# Summary

We chose to evaluate the effects of toxic air pollution on three health outcomes, mortality, low birth weight and cancer incidence.

### Mortality

Our analysis of the related effects of air pollution on mortality led us to the California Department of Health were we sourced aggregated mortality tables for all 58 California counties for a time scale spanning from 1999-2021. We focused our analysis on the top-ten most polluted CA counties, measured by the highest annual median AQI, and sourced morality statistics for heart disease, respiratory disease, and cancer. 

Using a Granger Causality hypothesis test, we determined that statistically significant relationships existed between toxic air pollution and counts of death from the four chosen causes of death in Imperial, Kern, Los Angeles, Riverside, San Bernardino, San Diego, and Tulare counties. In an effort to quantify the effect of the different monitored pollutants, a Poisson Regression model was selected to model counts of death per the four categories against days with elevated levels of fine air particulate (PM 2.5) and days with "good" air quality as assessed by Median AQI. 

The results showed marginal success but also much noise. We found that:

1. Kern County shows a statistically significant relationship between days with high levels of PM 2.5 and deaths from cancer, heart disease and respiratory illnesses. 

2. Los Angeles County shows a statistically significant relationship between days with high levels of PM 2.5 and deaths from cancer. 

3. Tulare County shows a statistically significant relationship between days with high levels of PM 2.5 and deaths from cancer. 

4. San Diego shows a statistically significant relationship between days with high levels of PM 2.5 and deaths from chronic lower respiratory disease. 

In all of the above models the regression coefficients indicated a negative relationship between good air quality days and a positive relationship between days with elevated levels of fine particulate matter, with p-values less than $.05$ for all coefficients. 


-- JACK PORTION
We conducted an analysis of the relationship between air quality and low birthweight in California. The data was collected from 2010 to 2021 and included county level information. Our initial analysis used a linear regression model with the air quality independent variables mentioned earlier in this summary.

However, due to the large number of variables and the presence of multicollinearity, we decided to perform a Lasso regression using LassoCV.

Our final model included the following independent variables:

'good days'
'max aqi'
'90th percentile aqi'
'days ozone'
'days pm10'

We found that 'good days' had a negative relationship with low birthweight as measured by a negative coefficient, while 'max aqi', '90th percentile aqi', and 'days ozone' had positive coefficients. 'Days pm10' had a strong negative coefficient, which may be explained removing the other contaminants from the original first model. The R-squared of the regression was 54.3%, and thus we focused our resourses on the other more successful datasets.

INSERT MORE

# Conclusion

INSERT MORE

