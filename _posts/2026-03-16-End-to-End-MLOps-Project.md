---
title: "Predicting California Housing Prices: An End-to-End MLOps Workflow"
author: Arnold Aijuka
date: 2026-03-16
categories: [Machine Learning, MLOps, Web Deployment]
tags: [python, scikit-learn, streamlit, knn, gridsearchcv]
image:
  path: /assets/californiaHousingML.jpg
  alt: Image of California Housing Predictor
---

# Why End-to-End MLOps?

Building a machine learning model is a great first step, but the true value is realized when that model is packaged, optimized, and deployed for end-users. In my project, **California Housing Price Predictor**, I focused on applying key concepts of pipeline construction, hyperparameter tuning, and model deployment.

## 1. The Challenge: Predicting Housing Values

The goal of this project was to build an end-to-end machine learning workflow to predict housing prices using the well-known California Housing dataset, which contains information collected from the 1990 California census. The target variable was the median house value, dependent on 8 features including median income, house age, and block group coordinates.

## 2. The Toolkit

To construct this pipeline and deploy it, I utilized:
* **Scikit-learn:** For data splitting, preprocessing, and the KNeighborsRegressor model.
* **GridSearchCV:** To find the best possible parameters for the model using 5-fold cross-validation.
* **Streamlit:** To host the model and provide an intuitive UI for users to input housing features.

## 3. Key Pipeline Steps

### Preprocessing and Pipeline Construction
After loading the dataset, I split the data into training and testing sets using an 80/20 ratio. I then built a preprocessing pipeline using a ColumnTransformer, which applied a standard scaler and simple imputer to all numeric columns. This ensured the data was properly scaled before being passed to the model.

### Hyperparameter Tuning
Instead of guessing the best model settings, I used GridSearchCV to systematically test different combinations of hyperparameters for the KNN model.
* I tuned the `n_neighbors` parameter by testing 3, 5, 7, and 9.
* I evaluated different `weights` strategies ('uniform' vs 'distance') and `p` values.
* The model was evaluated using the $R^2$ score to measure variance explanation, alongside MSE and RMSE.

### Model Deployment
Once optimized, I saved the trained pipeline using Pickle. Rather than stopping there, I integrated the `.pkl` model into a Streamlit web application. By pushing the code to a public GitHub repository and linking it to Streamlit, I created an interactive dashboard where users can input property details and instantly receive predicted house values.

---
*Stay tuned for my next post*
