# Capstone Project: Energy Market Forecasting

## Problem Statement

The government of Mexico has contracted you out as an energy markets consultant, and would like for you to develop models predicting energy prices in the Northeast region of the country. Coincidentally, you happen to be from Monterrey, the region's center of gravity when it comes to population size. You set out to see if you can, from the comfort of your apartment, build a model that can predict the price of energy reliably. You will, if time permits, also see if novel approaches in machine learning, such as LTSM RNNs, might allow the government to more reliably estimate the demand for energy.

## Data Sets

All energy demand, generation, and price data was pulled from APIs and databases that Mexico's National Center for Energy Control (CENACE) maintains. Weather data corresponding to Monterrey was also pulled from the OpenWeatherAPI on the intuition that weather can drive energy demand.

When it came to CENACE's energy price and demand data, we selected weighted price data corresponding to the region on the Mexican National Grid that Monterrey is in, as well as data on aggregate demand for energy within that region. When it came to generation, we got our hands on generation data at the national level, on the understanding that this generation all goes into the same grid. All generation, demand, and price data covers the period from 2019-2022 inclusive. So does the weather data. 

## Overview

This project repo contains 4 notebooks:

1. API Wrangling and EDA: Contains code for generating CENACE API calls and filtering their results.
2. A. Energy Price Modeling (ARIMAX): Contains code for modeling energy prices via an ARIMAX model.
2. B. Energy Price Modeling (ML): Contains code for modeling energy prices via a Random Forest Regressor, and compares said model's performance against a Linear Regression, a Ridge Regression, and a XGBoost model., 
2. C. Energy Price Demand Modeling (LTSM): Contains code for modeling energy demand via a LTSM RNN.

Of the two energy price models, it was XXXXXX that did better, achieving a RMSE < 300
Our LTSM model, on the other hand, performed poorly against the government's own demand estimates, with an average MAPE score that was roughly 2x higher than the government forecast average MAPE score.