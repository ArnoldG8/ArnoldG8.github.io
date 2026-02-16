---
title: "Scraping the Ice: Extracting Hockey Data with Python"
author: Arnold Aijuka
date: 2026-01-20
categories: [Data Science, Python, Web Scraping]
tags: [beautifulsoup, requests, pandas, data-collection]
---

# Why Web Scraping?

In the data world, not everything comes in a neat CSV file. Sometimes, the data you need is locked away on a website, visible to the eye but inaccessible to your analysis tools. That's where web scraping comes in.

In my recent assignment, **[Arnold_Aijuka_Web_Scrapping_CS-DA03-26044](https://colab.research.google.com/)**, I tackled the task of extracting structured hockey team data from a raw webpage and converting it into a usable dataset[cite: 12, 14, 23].

## 1. The Challenge: Unstructured HTML

The objective was straightforward but technical: scrape a specific table of hockey data from a website and export it into a CSV file. The data was embedded in HTML tags, meaning I had to parse the webpage structure to isolate the specific information I needed, such as Team Name, Year, Wins, and Losses[cite: 14, 88].

## 2. The Toolkit

To perform this extraction, I relied on the "holy trinity" of Python scraping libraries:
* **Requests:** To fetch the raw page content from the URL.
* **BeautifulSoup:** To parse the HTML and navigate the data structure (the `html.parser`).
* **Pandas:** To organize the scraped data into a structured DataFrame and export it.

## 3. Key Scraping Steps

### Fetching and Parsing
The process began by initializing a GET request to the target URL. Once I had the page text, I used BeautifulSoup to parse the content. The first major step was extracting the table headers (`th` tags) to serve as my DataFrame columns, stripping away any unnecessary whitespace to keep the data clean.

### Iterating Through Rows
The core of the work involved finding all table rows (`tr` tags). I wrote a loop to iterate through these rows, extracting the individual cell data (`td` tags). 

A crucial part of this step was data cleaning on the fly—ensuring that every text element was stripped of whitespace before being appended to the dataframe.

### Exporting the Result
Once the data was structured in a Pandas DataFrame, the final step was exporting it. I used the `.to_csv` command to save the cleaned data as `Hockey.csv`, ready for analysis.

---
*Stay tuned for my next posts!*
