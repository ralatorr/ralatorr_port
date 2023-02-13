# Ricardo Alatorre | Data Scientist | Chicago Booth MBA

## About Me

My name is Ricardo Alatorre, and I am a native of Monterrey, Nuevo León, México, where I've lived most of my life. I've also spent portions of my life in the United States, first as a college student in New York City, then as a business school student and senior program manager in Chicago. A committed student of mathematics, I've taken steps to develop my skills in quantitative modeling throughout the course of my career and have recently decided to pivot into data science, completing General Assembly's Data Science Immersive program in February 2023. I'm currently searching for roles in supply chain, energy, and retail.

Outside of work, I spend most of my leisure time cooking, gardening, and reading. I'm currently reading The Topeka School by Ben Lerner.

I do my best to maintain an active lifestyle, and try to run 3mi a few times a week.

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
After watching the US exit the World Cup, your American friends have decided to get into an argument at the cookout over what kind of sporting events they like to follow and why. Chief among their concerns is the question of which fandom is more annoying online - hockey fans or basketball fans. Naturally, each warring faction has decided to double down on the idea that it's actually the other fandom can stereotyped via their mannerisms, turns of phrase, and foolish notions of what makes for good sportsmanship.

You do not watch sports because you are a nerd and you like computers more, so you get a cheeky idea that is sure to annoy both sides. You tell them both fandoms are equally silly and simple-minded. Years from now, you will cringe at your use of the term "sportsball" and realize people don't talk to you at the water cooler because you're kind of tedious.

But today is not that day. You propose to write a computer program that takes training data in the form of Reddit forum posts corresponding to the NHL and the NBA, and you bet twenty dollars your computer program can correctly guess who wrote it - someone posting on r/NHL or someone posting on r/NBA. While your friends appreciate the awesome power of computers, they're not totally convinced that computers can process language in this specific way yet. What's your computer program going to do? Count words? Seems foolish.

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

1. Fine air particulate matter (PM 2.5)  had a statistically significant influence on deaths from heart disease, cancer and respiratory illnesses in the most polluted counties in California from 1999-2021. 
2. Time-series analysis allowed us to predict statewide cancer incidence rates for a handful of cancer types with MAPE rates at roughly 1.5%, with PM2.5, NO2 and Ozone often driving increases in incidence rates, but results should be taken with a grain of salt - aggregated data involved merely 20 year-by-year observations.

#### Link to Project
[California Health Outcomes](https://github.com/ralatorr/ralatorr.github.io/tree/main/Health_Outcomes)

### Energy Demand and Price Forecasting
#### Problem Statement

The government of Mexico has contracted you out as an energy markets consultant, and would like for you to develop models predicting energy prices in the Northeast region of the country. Coincidentally, you happen to be from Monterrey, the region's center of gravity when it comes to population size. You set out to see if you can, from the comfort of your apartment, build a model that can predict the price of energy reliably. You will, if time permits, also see if novel approaches in machine learning, such as LSTM RNNs, might allow the government to more reliably estimate the demand for energy.

#### Data Sets

All energy demand, generation, and price data was pulled from APIs and databases that Mexico's National Center for Energy Control (CENACE) maintains. Weather data corresponding to Monterrey was also pulled from the OpenWeatherAPI on the intuition that weather can drive energy demand.

When it came to CENACE's energy price and demand data, we selected weighted price data corresponding to the region on the Mexican National Grid that Monterrey is in, as well as data on aggregate demand for energy within that region. When it came to generation, we got our hands on generation data at the national level, on the understanding that this generation all goes into the same grid. All generation, demand, and price data covers the period from 2019-2022 inclusive. So does the weather data. 

#### Conclusions

Of the two energy price models, it was our Random Forest Regressor model that did the best, achieving a RMSE < 300 MXN.
Our LTSM model, on the other hand, had an average MAPE score that was roughly 2x higher than the government forecast average MAPE score.

#### Link to Project
[Energy Demand and Price Forecasting](https://github.com/ralatorr/ralatorr.github.io/tree/main/Energy_Forecasting)

## Contact
Contact me at the following:
- email: [ralatorr@chicagobooth.edu](ralatorr@chicagobooth.edu)
- LinkedIn: [https://www.linkedin.com/in/ricardoalatorre/](https://www.linkedin.com/in/ricardoalatorre/)
