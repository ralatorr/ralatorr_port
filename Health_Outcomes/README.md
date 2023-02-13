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

We chose to evaluate the effects toxic air pollution on three health outcomes, mortality, low birth weight and cancer incidence. 
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


### Low Birthrate Data & its Relationship with Air quality  
We conducted an analysis of the relationship between air quality and low birthweight in California. The data was collected from 2010 to 2022 and included county level information. Our initial analysis used a linear regression model with the air quality independent variables mentioned earlier in this summary.

However, due to the large number of variables and the presence of multicollinearity, we decided to perform a Lasso regression using LassoCV.

Our final model included the following independent variables:

1. 'good days'
2. 'max aqi'
3. '90th percentile aqi'
4. 'days ozone'
5. 'days pm10'

We found that 'good days' had a negative relationship with low birthweight as measured by a negative coefficient, while 'max aqi', '90th percentile aqi', and 'days ozone' had positive coefficients. 'Days pm10' had a strong negative coefficient, which may be explained removing the other contaminants from the original first model. 

The R-squared of the regression was 54.3%, and consequentially we chose to focus our resourses on the other more successful datasets for which we had promising modelling efforts.

### Relationship between Air Quality and Cancer Incidence
Finally, we conducted an analysis of the relationship between air quality and the incidence of several varieties of cancer in the state of California. While county-level information on cancer incidence rates is made available by the National Institutes of Health and the CDC, it is aggregated across 2015-2019 ([Source](https://statecancerprofiles.cancer.gov/incidencerates/index.php?stateFIPS=06&areatype=county&cancer=047&race=00&sex=0&age=001&stage=211&year=0&type=incd&sortVariableName=count&sortOrder=desc#results)). Year-by-year incidence rates are also available, but are aggregated at the state level ([Source](https://gis.cdc.gov/Cancer/USCS/#/Trends/)). To perform our analysis, we weighted county-level air quality data by the proportion of the state's population a given county represents in order to arrive at a weighted average of air quality measures for the entire state for the years 2000-2019.

We leveraged this data to create series of Autoregressive Integrated Moving Average Models with Exogenous regressors (ARIMAX models) that integrated time series data on cancer incidence rates and time series data on air quality measures for several different types of cancer.

Our models suggested a statistically significant direct relationship between days featuring with high concentrations of NO2, Ozone, and PM2.5 and the incidence of certain types of cancer, among them:

1. Cancer of the Oral Cavity and Pharynx
2. Pancreatic Cancer
3. Cervical Cancer
4. Female Breast Cancer

The models corresponding to these varieties of cancer did a decent job of predicting cancer incidence rates, often sporting Mean Absolute Percentage Error (MAPE) scores of rougly 1-2%. However, our results are qualified by the fact that our state-level cancer incidence and air quality data had been aggregated in such a way so as to provide only 20 observations to work with (corresponding to the years 2000-2019).

# Conclusions

1. Fine air particulate matter (PM 2.5)  had a statistically significant influence on deaths from heart disease, cancer and respiratory illnesses in the most polluted counties in California from 1999-2021. 
2. Time-series analysis allowed us to predict statewide cancer incidence rates for a handful of cancer types with MAPE rates at roughly 1.5%, with PM2.5, NO2 and Ozone often driving increases in incidence rates, but results should be taken with a grain of salt - aggregated data involved merely 20 year-by-year observations.
