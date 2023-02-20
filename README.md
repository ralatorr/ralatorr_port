# Ricardo Alatorre | Data Scientist | Chicago Booth MBA

## About Me

My name is Ricardo Alatorre, and I am a native of Monterrey, Nuevo León, México, where I've lived most of my life. I've also spent portions of my life in the United States, first as a college student in New York City, then as a business school student and senior program manager in Chicago. A committed student of mathematics, I've taken steps to develop my skills in quantitative modeling throughout the course of my career and have recently decided to pivot into data science, completing General Assembly's Data Science Immersive program in February 2023. I'm currently searching for data scientist roles in supply chain, energy, and retail.

Outside of work, I spend most of my leisure time cooking, gardening, and reading. I find that all three activities serve to put me at ease, cooking in particular. Lately I've been focsuing on preparing large quantities of curry over the weekends to give me something warm to eat on winter weekdays. When it comes to reading, I'm currently working my way through Normal People by Sally Rooney.

I do my best to maintain an active lifestyle, and generally make sure I run 3 miles a few times a week. I hope to be going back to the gym to lift more consistently very soon as well.

### Educational Background
- Certificate, Data Science, General Assembly
- University of Chicago Booth School of Business
  - M.B.A. (Econometrics & Statistics, Operations Management, and Analytic Finance)
- Columbia College, Columbia University
  - B.A. (Mathematics)  

### Professional Background / CV

I am a quantitative analyst with 6 years of experience spanning different roles in management consulting, renewable energy business development, and tech program management.

A PDF copy of my resume can be found here: [Ricardo Alatorre's Resume (PDF)](https://github.com/ralatorr/ralatorr.github.io/blob/main/Resume/Ricardo_Alatorre_Resume_2023.pdf).

## Project Portfolio
### NLP Reddit Classification
#### Problem Statement
After leveraging Pushshift API, we managed to collect several thousand posts from both the r/NBA and r/NHL subreddits. We then set out to build a model that would allow us to correctly classify a given post as having originated on either r/NBA or r/NHL. The exercise would serve as our first application of Natural Language Processing (NLP).

#### Summary of Findings

After performing some data cleaning and EDA, we found that roughly half of all submissions did not have bodies of text to process, although there was plenty of text data in submission titles that aided our modeling. Thus, the Titles and Selftext fields were appended together into a Fulltext column before being vectorized through TfidfVectorizer.

Three basic models were tested, with the following results:
Model (Train Score, Test Score)

    - Logistic Regression (97.6%, 94.2%)
        - LR, GridSearch (99%, 94.7%)
    - k-Nearest Neighbors (53%, 51%)
        - kNN, GridSearch (100%, 55%)
    - Random Forest (96.1%, 92.4%)
        - RF, Gridsearch (96.2, 91.0%)
    
Our most successful model turned out to be Logistic Regression under GridSearch, sporting the following classification metrics:

     - Accuracy (94.8%): Percentage of obsservations the model correctly predicted.
     - Misclassification Rate (5.2%): Percentage of observations the model incorrectly predicted.
     - Sensitivity (96.5%): Rate of True Positives vs All Positives (r/NHL)
     - Specificity (93.1%): Rate of True Negatives vs All Negatives (r/NBA)
     - Precision (93.4%): Rate of True Positives vs Predicted Positives (r/NHL)


#### Link to Project
[NLP Reddit Classification](https://github.com/ralatorr/ralatorr.github.io/tree/main/Reddit_Classification)

### California Health Outcomes
#### Problem Statement
Pollution has long been known to have a causal effect on negative health outcomes. Our group's goal was to use various statistical hypothesis tests as well as exploratory data analysis and regression analysis to gain a stronger quantitative understanding of the effects of air pollution amongst the 58 counties of California.

#### Conclusions

After careful review of the data, we found the following:

1. Fine air particulate matter (PM 2.5)  had a statistically significant influence on deaths from heart disease, cancer and respiratory illnesses in the most polluted counties in California from 1999-2021. 
2. Time-series analysis allowed us to predict statewide cancer incidence rates for a handful of cancer types with MAPE rates at roughly 1.5%, with PM2.5, NO2 and Ozone often driving increases in incidence rates, but results should be taken with a grain of salt - aggregated data involved merely 20 year-by-year observations.

#### Link to Project
[California Health Outcomes](https://github.com/ralatorr/ralatorr.github.io/tree/main/Health_Outcomes)

### Energy Demand and Price Forecasting
#### Problem Statement

After the energy market reforms of 2013, Mexico has seen its energy sector open up to private and foreign investment. We tried to see if we could build a model that could predict the price of energy, as well as demand, reliably in the real-time wholesale market.

All energy demand, generation, and price data was pulled from APIs and databases that Mexico's National Center for Energy Control (CENACE) maintains. Weather data corresponding to Monterrey was also pulled from the OpenWeatherAPI on the intuition that weather can drive energy demand.

When it came to CENACE's energy price and demand data, we selected weighted price data corresponding to the region on the Mexican National Grid that Monterrey is in, as well as data on aggregate demand for energy within that region. When it came to generation, we got our hands on generation data at the national level, on the understanding that this generation all goes into the same grid. All generation, demand, and price data covers the period from 2019-2022 inclusive. So does our weather data. 

#### Conclusions

We iterated on linear regression, time-series, and ML models.
Of our energy price models, our best-performing model was a Random Forest Regressor model which predicted the price of energy within 300 MXN /MWh (RMSE < 300)
We also developed a univariate Long Short-Term Memory (LSTM) model, a variety of Recurrent Neural Network (RNN), in order to model energy demand. This model had a Mean Absolute Percentage Error (MAPE) score roughly 2x as high as the government demand forecast MAPE score over the same period. Given the model was univariate, there's room for improvement in this model if it can be made multivariate and include time series of data such as temperature, among others.

#### Link to Project
[Energy Demand and Price Forecasting](https://github.com/ralatorr/ralatorr.github.io/tree/main/Energy_Forecasting)

## Contact
Contact me at the following:
- email: [ralatorr@chicagobooth.edu](ralatorr@chicagobooth.edu)
- LinkedIn: [https://www.linkedin.com/in/ricardoalatorre/](https://www.linkedin.com/in/ricardoalatorre/)
