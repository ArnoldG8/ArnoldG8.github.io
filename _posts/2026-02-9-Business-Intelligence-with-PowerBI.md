---
title: "Driving Hotel Revenue: A Power BI Business Intelligence Dashboard"
author: Arnold Aijuka
date: 2026-04-19
categories: [Business Intelligence, Data Analytics, Data Visualization]
tags: [power-bi, dax, data-modeling, dashboard, hospitality]
image:
  path: /assets/hotelPowerBI_Small.jpg
  alt: Image of Hotel Revenue Dashboard
---

# Why Business Intelligence?

Raw data is plentiful, but actionable business intelligence is rare. Bridging the gap between a database of booking records and a compelling visual story is essential for data-driven decision-making. In my project. 
In my recent project **[BI with PowerBI](https://app.powerbi.com/view?r=eyJrIjoiNDUyOTkxODAtODc5Ny00NjdjLWIzY2MtNjE2MGMyYTFjNDk4IiwidCI6IjE2ZDgzZWU2LTI1NGEtNDY5ZC1hNmNjLTU0ZTJjYTIzMTNlNyIsImMiOjh9)**I utilized Power BI to analyze a fictional five-star hotel chain to identify the root causes behind their declining revenue and market share.

## 1. The Challenge: From Raw Bookings to Insights

The hotel provided multiple raw datasets, including information on dates, rooms, and aggregated bookings. The goal was to clean this data, establish relationships between the tables, and calculate key performance indicators (KPIs) to create an interactive dashboard that speaks directly to business needs.

## 2. The Toolkit

To process and visualize this data, my stack included:
* **Power Query:** For cleaning data and promoting headers.
* **Power BI Data Modeling:** To construct a Star Schema connecting foreign keys to primary keys.
* **Data Analysis Expressions (DAX):** To compute advanced measures and calculated columns.

## 3. Key Implementation Steps

### Data Loading and Transformation
The process started by importing the raw CSV files from a local folder into Power BI. Using the Power Query editor, I transformed the data by making the first rows the headers and removing unnecessary columns to ensure a clean starting point.

### Data Modeling
With clean data, I built the underlying data model. I created a Star Schema by linking fields that served as foreign keys in the fact tables (like `fact_bookings`) to the primary keys in the dimension tables (like `dim_hotels` and `dim_rooms`).

### DAX Measures and Dashboard Creation
To enable meaningful visualization, I wrote several DAX expressions to calculate crucial hospitality metrics:
* **Revenue:** `SUM(fact_bookings[revenue_realized])`
* **Occupancy %:** `DIVIDE([Total Successful Bookings], [Total Capacity], 0)`
* **Average Rating:** `AVERAGE(fact_bookings[ratings_given])`

These measures powered a highly interactive dashboard featuring trends by key metrics, realization rates by booking platform, and detailed property-level analytics, allowing stakeholders to easily pinpoint performance gaps.

---
*Stay tuned for my next post*
