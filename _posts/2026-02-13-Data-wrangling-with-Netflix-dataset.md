---
title: "A Deep Dive into Netflix Data Wrangling"
author: Arnold Aijuka
date: 2026-02-13
categories: [Data Science, Python, Data Wrangling]
tags: [pandas, kaggle, netflix, data-cleaning, numpy]
---

# Why the Data Wrangling?

In the world of data science, the glamour often lies in predictive models and flashy dashboards. But any experienced practitioner knows the truth: **Quality comes from data wrangling, if you put in garbage, you will get garbage insights.**

In my recent project, **[Arnold Aijuka Netflix Data Wrangling Project](https://www.kaggle.com/code/arnoldaijuka/arnold-aijuka-netflix-data-wrangling-project)**, I took on the infamous Netflix Movies and TV Shows dataset to demonstrate the critical process of transforming raw, messy data into a structured format ready for analysis.

## 1. The Challenge: Raw Data

The dataset contains listings of all the movies and TV shows available on Netflix, including details like cast, directors, ratings, and release years. While rich in information, it suffers from common real-world data issues:
* **Missing Values:** Critical columns like `director`, `cast`, and `country` had significant gaps.
* **Inconsistent Formats:** Dates were stored as strings.
* **Nested Data:** The `listed_in` (genre) column contained multiple categories in a single string.

## 2. The Toolkit

To tackle this, I utilized the standard Python data stack:
* **Pandas:** for data manipulation and cleaning.
* **NumPy:** for numerical operations.
* **Matplotlib & Seaborn:** for initial exploratory visualization.

## 3. Key Wrangling Steps

### Handling Missing Data
One of the first steps was identifying null values. Instead of simply dropping rows (which would lose valuable data), I applied specific strategies:
* **Imputation:** For the `director` column, I filled missing values with the most frequent director based on a cast or a placeholder like "Not Given" to maintain dataset integrity.
* **Contextual Filling:** For `rating`, I investigated the missing rows and filled them based on context or dropped the insignificant number of nulls.

### Date & Time Standardization
The `date_added` column is crucial for understanding Netflix's content strategy over time. I converted this from an object (string) type to a proper `datetime` format. This allowed me to extract:
* **Year Added**
* **Month Added**

---
*Stay tuned for my next post*
