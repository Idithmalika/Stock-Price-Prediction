# AAPL Stock Price Analysis & LSTM Forecasting

## Project Overview

This project explores the use of Long Short-Term Memory (LSTM) neural networks to forecast Apple Inc. (AAPL) stock prices using historical market data.

The project compares two LSTM approaches against a simple Naive Baseline:

- Naive Baseline
- Univariate LSTM
- Multivariate LSTM

The goal was not only to build machine learning models, but also to evaluate whether the more complex models actually provided an improvement over a simple forecasting strategy.

## Objectives

The main objectives of this project were to:

- Collect historical AAPL stock market data
- Perform exploratory data analysis
- Analyze daily returns and price trends
- Calculate moving averages
- Build a Naive Baseline model
- Build a Univariate LSTM model
- Build a Multivariate LSTM model
- Evaluate models using MAE and RMSE
- Compare complex machine learning models against a simple benchmark
- Communicate the results and limitations of the models



## Dataset

Historical AAPL stock data was collected using the `yfinance` Python library.

**Ticker:** AAPL  
**Period:** January 2015 – December 2025

The dataset contains:

- Open
- High
- Low
- Close
- Volume

Additional features were engineered:

- Daily Return
- 20-Day Moving Average (MA20)
- 50-Day Moving Average (MA50)



##  Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- TensorFlow
- Keras
- yfinance
- Jupyter Notebook



## Exploratory Data Analysis

The project examined:

### Stock Price Trends

Historical closing prices were visualized to understand long-term price movements.

### Daily Returns

Daily percentage returns were calculated to examine short-term price changes and volatility.

### Moving Averages

20-day and 50-day moving averages were calculated to identify trends and smooth short-term price fluctuations.



## Models

## Naive Baseline

The Naive Baseline predicts the next closing price using the previous closing price.

This provides a simple benchmark to determine whether the machine learning models provide meaningful improvement.

### 2. Univariate LSTM

The first neural network uses historical closing prices as the input.

The model uses a 60-day lookback window to predict the next closing price.

Architecture:

- LSTM: 64 units
- LSTM: 64 units
- Dense: 32 units
- Dropout: 20%
- Output: 1 value

### 3. Multivariate LSTM

The second neural network uses multiple market features:

- Open
- High
- Low
- Close
- Volume
- Daily Return
- MA20
- MA50

The same 60-day lookback approach was used.



## Model Evaluation

Models were evaluated using:

### Mean Absolute Error (MAE)

MAE measures the average absolute difference between predicted and actual prices.

Lower values indicate better performance.

### Root Mean Squared Error (RMSE)

RMSE penalizes larger prediction errors more heavily.

Lower values indicate better performance.

### Results

| Model | MAE | RMSE |
|---|---:|---:|
| Naive Baseline | 2.4169 | 3.5735 |
| Univariate LSTM | 12.3161 | 13.9052 |
| Multivariate LSTM | 18.8246 | 20.5452 |

---

##  Key Findings

The Naive Baseline achieved the best performance on the selected test period.

The results show:

1. The simple baseline outperformed both LSTM models.
2. The Univariate LSTM performed better than the Multivariate LSTM.
3. Adding additional features did not automatically improve forecasting accuracy.
4. Model complexity alone does not guarantee better predictive performance.

This was an important finding because it demonstrates why machine learning models should always be compared against appropriate baseline models.

---

## Limitations

This project has several limitations:

- The models rely primarily on historical market data.
- Stock prices are affected by news, market sentiment, economic conditions, and company fundamentals.
- Only one chronological train/test split was used.
- Extensive hyperparameter optimization was not performed.
- Transaction costs and slippage were not included.
- The project predicts price levels rather than directly optimizing investment returns.
- Historical performance does not guarantee future results.

---

## Future Improvements

Potential improvements include:

- Walk-forward validation
- Rolling-window evaluation
- Hyperparameter optimization
- Predicting returns instead of raw prices
- Additional technical indicators
- Market index data
- Macroeconomic variables
- News sentiment
- XGBoost and Random Forest models
- Transformer-based time-series models
- More extensive backtesting
- Transaction costs and slippage

---

## Project Structure

```text
Stock-Price-Prediction/
│
├── data/
│   └── model_comparison.csv
│
├── images/
│   ├── actual_vs_predicted.png
│   ├── daily_returns.png
│   ├── moving_averages.png
│   ├── multivariate_lstm_predictions.png
│   ├── model_comparison_mae.png
│   ├── model_comparison_rmse.png
│   └── model_comparison_table.png
│
├── notebooks/
│   └── stock_prediction.ipynb
│
├── README.md
└── requirements.txt