# 🎬 Netflix Movie IMDB Score Prediction using Machine Learning

## 📌 Project Overview
This project aims to predict the IMDB score of a movie prior to its release by analyzing various features from Netflix movie data. Unlike traditional studies that focus on box office predictions, this project focuses on predicting consumer ratings (IMDB Scores) to help OTT platforms discover hidden gems and provide alternative evaluation metrics for negotiations between OTT platforms and production companies.

## 🛠️ Data & Preprocessing
*   **Dataset:** Netflix movies data from Kaggle (2015.04 - 2021.03).
*   **Data Cleaning:** Handled duplicate records and missing values. Converted variables like 'Number of Actors' and 'Number of Available Countries' into numerical formats.
*   **Feature Engineering:**
    *   Grouped 28 distinct genres into 5 broader categories (A to E) based on similarity to reduce feature dimensions.
    *   Created dummy variables for categorical features such as 'Series/Movie', 'Runtime', and the newly categorized 'Genres'.
*   **Exploratory Data Analysis (EDA):** Analyzed trends in movie releases over the years, specifically highlighting the impact of the COVID-19 era on Netflix releases. Investigated correlations between variables (e.g., strong positive correlation between 'Runtime' and 'Series/Movie').

## 🤖 Modeling Strategy
Initially, I approached this as a **Regression problem** to predict the exact IMDB score. However, due to the complex nature of movie ratings and multiple influencing factors, the performance of regression models (e.g., Ridge, Lasso, RandomForest) was suboptimal.

**💡 Strategic Shift: From Regression to Classification**
Based on prior research on movie box-office predictions, I converted the target variable (IMDB Score) from a continuous variable into a **categorical variable** by dividing it into quartiles (0 to 3). This shift to a classification problem significantly improved model accuracy.

## 🚀 Key Results & Ensemble Approach
*   **Evaluated Models:** Tested various classification models including Logistic Regression, SVM, Random Forest, XGBoost, LightGBM, and Extra Trees.
*   **Ensemble Model:** Applied a **Hard Voting Ensemble** combining KNN, Extra Tree, XGBoost, Random Forest, SGD, SVM, Decision Tree, and LightGBM, which achieved the highest Training Score (0.5629).
*   **Feature Importance:** Found that 'Number of Actors' and 'Number of Available Countries' had a more significant impact than specific movie genres.
*   **Real-world Application:** Successfully predicted the IMDB score category for the movie *"The Boy and the Heron"* using the trained XGBoost Classifier.

## 🤔 Limitations & Future Work
*   **Data Size:** The dataset size was limited, impacting the test accuracy.
*   **Feature Enrichment:** Future iterations should include more influential features such as critic reviews, existence of original works, and sentiment analysis from scraped reviews.
