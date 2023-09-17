# Marketing Linear regression

## Table of Contents
- [Project Overview](#project-overview)
- [Data Acquisition and Initial Exploration](#data-acquisition-and-initial-exploration)
- [Data Cleaning](#data-cleaning)
- [Feature Engineering](#feature-engineering)
- [Baseline Model Training](#baseline-model-training)
- [User Visit Analysis](#user-visit-analysis)
- [Conclusion](#conclusion)

---

## Project Overview

This project involves the analysis of a dataset and the development of a baseline regression model for predicting transaction revenue. The dataset was initially loaded, and data exploration was performed to understand the structure and nature of the data. Subsequently, data cleaning was carried out to handle missing values and outliers. The dataset was also transformed and engineered to create relevant features for modeling.

A baseline linear regression model was trained on the processed data to predict transaction revenue. Finally, user visit analysis was conducted to gain insights into user behavior and interactions.

---

## Data Acquisition and Initial Exploration

The project began with the acquisition of a dataset stored in a CSV file named 'train.csv'. The dataset was loaded into a Pandas DataFrame for further analysis. An initial exploration was performed to examine the structure of the data, and the first few rows of the dataset were displayed using `df.head()`.

---

## Data Cleaning

### Columns to Expand

Several columns in the dataset, including 'trafficSource,' 'device,' 'totals,' and 'geoNetwork,' contained JSON-like structures. To make these columns more usable, they were expanded into separate Pandas DataFrames and concatenated into the main DataFrame. The original columns were then dropped.

### Handling Unhashable Type

Some columns, such as 'adwordsClickInfo,' contained unhashable types (e.g., dictionaries), causing errors when attempting to find unique values. These columns were identified and dropped from the DataFrame.

### Removing Columns with Only One Unique Value

Columns with only one unique value across all rows, such as 'socialEngagementType' and 'visitStartTime,' were removed as they do not provide meaningful information for modeling.

### Scaling Transaction Revenue

The 'transactionRevenue' column, representing revenue, was scaled by dividing it by 10^5. Missing values in this column were filled with zeros.

---

## Feature Engineering

To prepare the data for modeling, feature engineering was performed. A new DataFrame was created by grouping data by 'fullVisitorId' and aggregating numerical features. The following features were aggregated for each user:
- 'bounces'
- 'hits'
- 'newVisits'
- 'transactionRevenue'
- 'pageviews'

---

## Baseline Model Training

The dataset was split into training and testing sets, and a baseline linear regression model was trained using the 'fullVisitorId' as the target variable and the aggregated features as input. The model's predictions were compared to the actual revenue values to assess its performance.

---

## User Visit Analysis

User visit analysis was conducted by analyzing user behavior and interactions. Key insights and statistics were derived from the user-level data.

---

## Conclusion

This project involved the exploration, cleaning, and preprocessing of a dataset for regression modeling, specifically for predicting transaction revenue. A baseline linear regression model was trained, and initial insights into user visits were obtained. Further analysis and model improvements can be explored in future iterations of this project.
