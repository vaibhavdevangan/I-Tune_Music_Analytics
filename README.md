# 📊 iTunes Dataset Cleaning & Preparation Report

## Project: iTunes Dataset Analysis
Prepared By: @vaibhavdevangan
Date: 21/02/2026

### 1. Introduction

This report documents the data cleaning and preparation process performed on the iTunes dataset. The cleaned dataset is ready for exploratory data analysis (EDA), feature engineering, and predictive modeling tasks.

### 2. Dataset Overview

Original Rows: 4,915

Original Columns: 15

Columns Retained After Cleaning: 9

Remaining Columns:

track_id

track_name

artist_name

collection_name

genre

track_price

collection_price

release_date

track_time_millis

### 3. Cleaning & Preprocessing Steps

Dropped Columns
Removed irrelevant or non-informative columns:
album_artist, currency, preview_url, artwork_url, country, rating.

Handled Invalid Values

Replaced invalid prices -1 in track_price and collection_price with NaN.

Converted Data Types

Column	Type Conversion
track_id	string/object
track_price	float64
collection_price	float64
release_date	datetime64[ns, UTC]
track_time_millis	int64

Missing Values Check

Column	Missing Values	Decision
artist_name	2	Retain
track_price	409	Retain
collection_price	402	Retain
release_date	48	Retain

Reason for not handling missing values: Proportion of missing data is small; it will not significantly impact initial analysis.

Dataset Summary (Numeric Columns)

Column	Count	Mean	Min	Max
track_price	4506	1.214	0.69	1.29
collection_price	4513	8.678	0.69	119.99
track_time_millis	4915	239568	30503	4676058
### 4. Output

Cleaned Dataset: cleaned_data.csv

Export Note: index=False used to avoid writing row numbers to the CSV.

### 5. Next Steps

Exploratory Data Analysis (EDA)

Visualize distributions of numeric and categorical features

Identify outliers and anomalies

Study feature relationships

Feature Engineering & Preprocessing

Encode categorical variables

Scale numeric features

Handle remaining missing values if necessary

Predictive Modeling & Insights

Regression or classification modeling

Extract actionable insights on tracks, collections, pricing, and genre trends

✅ This cleaned dataset is now ready for analytics pipelines and subsequent ML model development.
