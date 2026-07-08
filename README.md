# YES BANK Stock Price Prediction

## Project Overview

This project performs Exploratory Data Analysis (EDA) and Machine Learning on historical monthly YES BANK stock price data.

The main objective is to analyse stock price patterns and build regression models to estimate the monthly closing price using Open, High, and Low prices.

## Dataset

The dataset contains the following features:

- Date
- Open
- High
- Low
- Close

## Exploratory Data Analysis

The EDA notebook contains 20 meaningful visualizations covering:

- Stock price trends over time
- Distribution analysis
- Outlier analysis
- Correlation analysis
- Monthly price range
- Open-to-Close percentage change
- Univariate analysis
- Bivariate analysis
- Multivariate analysis

## Machine Learning Models

The following regression models were implemented and compared:

1. Linear Regression
2. Ridge Regression
3. Random Forest Regressor

## Model Evaluation Metrics

The models were evaluated using:

- Mean Absolute Error (MAE)
- Root Mean Squared Error (RMSE)
- R² Score

Hyperparameter tuning was also performed to improve model performance.

## Project Files

- `EDA_YesBank_StockPrices_Project.ipynb` — Detailed EDA with 20 charts
- `ML_YesBank_StockPrices_project.ipynb` — Machine Learning model development and evaluation
- `data_YesBank_StockPrices.csv` — Dataset used for the project

## Tools and Technologies

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- SciPy
- Joblib
- Google Colab

## Conclusion

The project demonstrates a complete data science workflow, including data understanding, cleaning, exploratory data analysis, feature selection, model training, hyperparameter tuning, evaluation, and model saving.

The relationships among Open, High, Low, and Close prices support the use of regression-based machine learning models for closing-price estimation.

## Author

**Janani M**  
M.Sc. Data Science Student  
Aspiring Data Analyst
