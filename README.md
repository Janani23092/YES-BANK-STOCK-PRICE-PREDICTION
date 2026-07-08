# 📈 YES BANK Stock Closing Price Prediction

![Python](https://img.shields.io/badge/Python-3.x-blue)
![Machine Learning](https://img.shields.io/badge/Machine%20Learning-Regression-orange)
![EDA](https://img.shields.io/badge/EDA-20%20Visualizations-green)
![Models](https://img.shields.io/badge/Models-3-purple)
![Status](https://img.shields.io/badge/Project-Completed-success)

## 📌 Project Overview

This project presents a complete **Exploratory Data Analysis (EDA) and Machine Learning Regression workflow** using historical monthly stock-price data of **YES BANK**.

The primary objective is to analyse historical stock-price behaviour, identify important relationships among the variables, and build regression models to estimate the monthly **Close price** using:

- Open price
- High price
- Low price

The project covers the complete data science lifecycle, including:

- Data understanding
- Data cleaning and preprocessing
- Exploratory Data Analysis
- 20 meaningful visualizations
- Statistical hypothesis testing
- Feature engineering
- Feature selection
- Chronological train-test splitting
- Machine learning model development
- Hyperparameter tuning
- Model evaluation and comparison
- Final model selection
- Model saving and loading
- Sanity-check prediction

---

## 🎯 Business Objective

The objective of this project is to develop a data-driven system that can estimate the monthly closing price of YES BANK stock using historical Open, High, and Low prices.

The project also aims to:

- Understand long-term stock-price trends
- Identify periods of high volatility
- Study relationships among OHLC variables
- Determine the strongest predictors of Close price
- Compare multiple regression algorithms
- Select a simple, accurate, and interpretable final model

> **Important:** The model is intended as a decision-support and educational tool. It should not be considered a guaranteed stock-market forecasting system or financial advice.

---

## 📊 Dataset Overview

The dataset contains historical monthly YES BANK stock-price observations from **July 2005 to November 2020**.

| Feature | Description |
|---|---|
| `Date` | Month and year of the stock-price observation |
| `Open` | Opening stock price for the month |
| `High` | Highest stock price recorded during the month |
| `Low` | Lowest stock price recorded during the month |
| `Close` | Closing stock price and target variable |

### Dataset Summary

- **Number of records:** 185
- **Number of original columns:** 5
- **Missing values:** 0
- **Duplicate records:** 0
- **Target variable:** `Close`

---

## 🧹 Data Cleaning and Preprocessing

The following preprocessing steps were performed:

- Converted the `Date` column into datetime format
- Sorted the observations chronologically
- Checked for missing values
- Checked for duplicate records
- Examined data types
- Analysed statistical outliers
- Retained genuine historical extreme stock prices
- Created additional analytical features

### Engineered Features

#### Monthly Price Range

```text
Monthly_Range = High - Low
