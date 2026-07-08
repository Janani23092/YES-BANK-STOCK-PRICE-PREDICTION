# 📈 YES BANK Stock Closing Price Prediction

## 📌 Project Overview

This project presents a complete **Exploratory Data Analysis (EDA) and Machine Learning Regression workflow** using historical monthly stock price data of **YES BANK**.

The main objective is to analyze historical stock price behavior, identify important patterns and relationships, and build regression models to estimate the monthly **Closing Price** using:

- Open Price
- High Price
- Low Price

The project covers the complete data science workflow, including:

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

- Understand long-term stock price trends
- Identify periods of high volatility
- Study relationships among OHLC variables
- Determine the strongest predictors of Close price
- Compare multiple regression algorithms
- Select a simple, accurate, and interpretable final model

> **Note:** This project is intended for educational and decision-support purposes only. It should not be considered financial advice or a guaranteed stock market forecasting system.

---

## 📊 Dataset Overview

The dataset contains historical monthly YES BANK stock price observations from **July 2005 to November 2020**.

| Feature | Description |
|---|---|
| `Date` | Month and year of the stock price observation |
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
- Analyzed statistical outliers
- Retained genuine historical extreme stock prices
- Created additional analytical features

### Engineered Features

#### Monthly Price Range

```text
Monthly_Range = High - Low
```

This feature represents the difference between the highest and lowest price recorded during a month and acts as a simple indicator of monthly volatility.

#### Percentage Change

```text
Pct_Change = Percentage change in Close price
```

This feature helps identify unusually strong positive and negative monthly movements.

---

## 📈 Exploratory Data Analysis

The EDA notebook contains **20 meaningful visualizations** covering univariate, bivariate, multivariate, and time-series analysis.

The analysis includes:

- Closing price trend over time
- Distribution of stock price variables
- Boxplot and outlier analysis
- Open vs. Close relationship
- High vs. Close relationship
- Low vs. Close relationship
- Correlation heatmap
- Pair plot analysis
- OHLC price comparison
- Yearly stock price trend
- Calendar-month analysis
- Monthly price range analysis
- Percentage-change analysis
- Rolling trend and volatility analysis
- Multivariate relationship analysis

---

## 🔍 Key EDA Insights

### 1. Strong Long-Term Price Movement

The stock experienced a long growth period followed by a sharp decline during the later years of the dataset.

### 2. Right-Skewed Price Distributions

The stock price variables are strongly right-skewed because most observations occur at lower and moderate price levels, while fewer observations belong to historically high-price periods.

### 3. Extreme Values Are Genuine

High-price statistical outliers were retained because they represent real historical market behavior rather than data-entry errors.

### 4. Strong Relationships Among OHLC Variables

Open, High, Low, and Close prices move closely together throughout the historical period.

### 5. Low Price Has the Strongest Relationship with Close

Among the selected independent variables, `Low` showed the strongest linear relationship with the target variable `Close`.

### 6. Volatility Changes Over Time

The monthly High-Low range shows that volatility is not constant. Some periods contain much larger price movements than others.

---

## 🧪 Hypothesis Testing

Statistical tests were performed to validate important patterns observed during EDA.

The analysis included:

- Pearson correlation testing
- Comparison of stock price behavior across different periods
- Volatility comparison

The tests supported the strong relationship between the independent variables and the target variable and confirmed meaningful changes in stock behavior over time.

---

## ⚙️ Feature Selection

The following independent variables were selected:

```text
Open
High
Low
```

The target variable is:

```text
Close
```

These features were selected because they have strong relationships with the monthly closing price.

---

## ⏳ Train-Test Split Strategy

A **chronological 80:20 train-test split** was used instead of a random split.

### Training Data

- First 80% of observations
- 148 monthly records

### Testing Data

- Final 20% of observations
- 37 monthly records

Using a chronological split ensures that the model is trained using earlier historical observations and evaluated using later observations.

This reduces the risk of future information leaking into the training process.

---

## 🤖 Machine Learning Models

Three regression models were implemented and compared.

### 1️⃣ Linear Regression

Linear Regression was used as the primary baseline model.

It is:

- Simple
- Fast
- Interpretable
- Suitable for strongly linear relationships

### 2️⃣ Ridge Regression

Ridge Regression was used to handle the strong correlations among Open, High, and Low prices.

Hyperparameter tuning was performed to identify the best regularization strength.

### 3️⃣ Random Forest Regressor

Random Forest was used as a nonlinear ensemble model.

Hyperparameter tuning was performed to optimize model settings such as:

- Number of trees
- Maximum tree depth

---

## 🔧 Hyperparameter Tuning

Hyperparameter tuning was performed using:

- `GridSearchCV`
- Time-series-aware validation

The tuned models included:

- Ridge Regression
- Random Forest Regressor

---

## 📏 Model Evaluation Metrics

The models were evaluated using three regression metrics.

### Mean Absolute Error (MAE)

Measures the average absolute difference between actual and predicted values.

### Root Mean Squared Error (RMSE)

Measures prediction error while giving a larger penalty to large mistakes.

### R² Score

Measures how much variation in the target variable is explained by the model.

A higher R² score and lower MAE and RMSE values indicate better model performance.

---

## 🏆 Model Comparison

| Model | Test R² | MAE | RMSE |
|---|---:|---:|---:|
| Linear Regression | 0.9848 | ₹9.78 | ₹15.82 |
| Ridge Regression | 0.9848 | ₹9.79 | ₹15.82 |
| Random Forest Regressor | 0.9709 | ₹13.96 | ₹21.85 |

---

## 🥇 Final Model

### Linear Regression

Linear Regression was selected as the final model because it achieved:

- **R² Score:** 0.9848
- **MAE:** ₹9.78
- **RMSE:** ₹15.82

It was selected because it provides:

- High predictive performance
- Simple implementation
- Fast training
- Easy interpretation
- Strong transparency

The more complex Random Forest model did not provide better performance for this dataset.

---

## 💾 Model Saving and Sanity Check

The final trained model and preprocessing scaler were saved using **Joblib**.

The saved model and scaler were loaded again to verify that they could be reused successfully.

### Sanity-Check Prediction

```text
Input:
Open = ₹12.41
High = ₹14.90
Low  = ₹12.21

Predicted Close = ₹14.64
Actual Close    = ₹14.67
```

The close agreement between the predicted and actual values confirms that the saved model can be loaded and used successfully.

---

## 💡 Business Recommendations

Based on the analysis:

1. Open, High, and Low prices can be used as important inputs for estimating the monthly Close price.

2. Periods with a rapidly increasing High-Low range should be treated as higher-risk market conditions.

3. Historical extreme values should not be removed automatically because they may represent genuine market events.

4. A simple and interpretable model can outperform a more complex model when relationships in the data are strongly linear.

5. The model should be used together with human judgment and additional market information.

---

## 🛠️ Tools and Technologies

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- SciPy
- Scikit-learn
- Joblib
- Google Colab
- Jupyter Notebook
- GitHub

---

## 📁 Project Structure

```text
YES-BANK-STOCK-PRICE-PREDICTION/
│
├── EDA_YesBank_StockPrices_Project.ipynb
│   └── Detailed EDA with 20 visualizations
│
├── ML_YesBank_StockPrices_Project.ipynb
│   └── ML model development, tuning and evaluation
│
├── data_YesBank_StockPrices.csv
│   └── Historical YES BANK stock price dataset
│
├── YesBank_Stock_Prediction_Presentation.pptx
│   └── Project presentation
│
└── README.md
    └── Complete project documentation
```

---

## 📌 Project Workflow

```text
Business Understanding
        ↓
Data Collection
        ↓
Data Understanding
        ↓
Data Cleaning
        ↓
Exploratory Data Analysis
        ↓
Hypothesis Testing
        ↓
Feature Engineering
        ↓
Feature Selection
        ↓
Chronological Train-Test Split
        ↓
Model Training
        ↓
Hyperparameter Tuning
        ↓
Model Evaluation
        ↓
Final Model Selection
        ↓
Model Saving and Sanity Check
        ↓
Conclusion and Recommendations
```

---

## ✅ Project Status

**Completed**

- [x] Data Understanding
- [x] Data Cleaning
- [x] 20 EDA Visualizations
- [x] Hypothesis Testing
- [x] Feature Engineering
- [x] Feature Selection
- [x] Chronological Train-Test Split
- [x] Three Machine Learning Models
- [x] Hyperparameter Tuning
- [x] Model Evaluation
- [x] Final Model Selection
- [x] Model Saving
- [x] Sanity-Check Prediction
- [x] Project Presentation
- [x] GitHub Documentation

---

## 👩‍💻 Author

### Janani M
https://www.linkedin.com/in/janani-m-0211b63bb

If you found this project useful, consider giving the repository a ⭐.
