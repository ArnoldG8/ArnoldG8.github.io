---
title: "Navigating the Titanic Dataset: A Deep Dive into EDA"
author: Arnold Aijuka
date: 2026-02-16
categories: [Data Science, Python, EDA]
tags: [seaborn, titanic, missingno, visualization, statistics]
---

# Why Exploratory Data Analysis?

Before we can build predictive models, we must understand the story the data is trying to tell us. Exploratory Data Analysis (EDA) is that crucial first step where we uncover patterns, spot anomalies, and test hypotheses.

In my latest project, **[Arnold Aijuka Exploratory Data Analysis Project](https://www.kaggle.com/code/arnoldaijuka)**, I performed a comprehensive EDA on the famous Titanic dataset to understand the factors that influenced survival rates.

## 1. The Challenge: Missing Data and Outliers

The Titanic dataset is rich but messy. Upon initial inspection, I found 891 rows of data, but significant gaps existed.
* **Missing Values:** The `Cabin` column had over 600 missing values, and `Age` had gaps that needed intelligent filling.
* **Outliers:** Statistical outliers in `Fare` and `Age` threatened to skew potential analysis.

## 2. The Toolkit

To tackle this, I utilized a robust Python stack:
* **Pandas & Numpy:** For data manipulation.
* **Seaborn & Matplotlib:** For high-quality visualizations.
* **Missingno:** A specialized library for visualizing missing data patterns.
* **Scipy:** For statistical outlier detection (Z-score).

## 3. Key EDA Steps

### Handling Missing Data
I started by visualizing the missing data using `msno.bar()`. The `Cabin` column was too sparse to save, so I dropped it. For `Age` and `Fare`, rather than deleting rows, I imputed missing values using the mean and median, respectively, to preserve the dataset's size.

### visual Analysis
I broke the analysis down into three layers:
1.  **Univariate:** I used histograms and KDE plots to look at the distribution of Age and Fare, identifying a right-skewed distribution in ticket prices.
2.  **Bivariate:** Using Violin plots, I analyzed the relationship between Age and Survival, noting that survivors tended to be between 20 and 48 years old.
3.  **Multivariate:** I employed a correlation heatmap to quantify relationships, such as the negative correlation between Class (`Pclass`) and Fare. I also used Mosaic plots to visualize the density of survivors across different passenger classes.

### Outlier Detection
Finally, I applied statistical methods to clean the data further. Using Z-scores, I identified 7 outliers in the `Age` column, and using the Interquartile Range (IQR) method, I detected 116 outliers in `Fare`.

---
*Stay tuned for my next post!*
