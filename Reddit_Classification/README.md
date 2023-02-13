# Project 3: Web APIs & NLP

## Problem Statement

After watching the US exit the World Cup, your American friends have decided to get into an argument at the cookout over what kind of sporting events they like to follow and why. Chief among their concerns is the question of which fandom is more annoying online - hockey fans or basketball fans. Naturally, each warring faction has decided to double down on the idea that it's actually the other fandom can stereotyped via their mannerisms, turns of phrase, and foolish notions of what makes for good sportsmanship.

You do not watch sports because you are a nerd and you like computers more, so you get a cheeky idea that is sure to annoy both sides. You tell them both fandoms are equally silly and simple-minded. Years from now, you will cringe at your use of the term "sportsball" and realize people don't talk to you at the water cooler because you're kind of tedious.

But today is not that day. You propose to write a computer program that takes training data in the form of Reddit forum posts corresponding to the NHL and the NBA, and you bet twenty dollars your computer program can correctly guess who wrote it - someone posting on r/NHL or someone posting on r/NBA. While your friends appreciate the awesome power of computers, they're not totally convinced that computers can process language in this specific way yet. What's your computer program going to do? Count words? Seems foolish.


## Summary of Findings

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

## Next Steps

We determined that our kNN model is not suited to the task given the high degree of dimensionality in the data. However, we'd like to examine more sets of parameters to iterate through GridSearch so as to improve the perfromance of the LR and RF models meaningfully compared to the base case of each.