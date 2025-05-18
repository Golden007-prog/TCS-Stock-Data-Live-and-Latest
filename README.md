# TCS Stock Data Latest
![gg](https://github.com/user-attachments/assets/4f39512b-8ec9-4694-9ea7-263cde7e45b8)

---
A complete data science project that explores, analyzes, and forecasts **Tata Consultancy Services (TCS)** stock performance using technical indicators, machine learning, deep learning, and interactive dashboards.

---
## System Architecture Star Diagram

![Screenshot 2025-05-18 041618](https://github.com/user-attachments/assets/a83fcbee-ec7c-43f4-bb8c-d9c5ca71e8a6)

---

## Objective

Analyze over 20 years of TCS stock data to extract insights, visualize trends, and forecast future prices using classical machine learning models (Linear Regression, Random Forest, XGBoost), deep learning (LSTM), and time-series forecasting (Prophet).

---

## Dataset Overview

This project uses three datasets:

- `TCS_stock_history.csv` – Daily OHLCV (Open, High, Low, Close, Volume) data
- `TCS_stock_action.csv` – Corporate actions like stock splits & dividends
- `TCS_stock_info.csv` – Stock metadata and summary stats

> All datasets are cleaned, feature-engineered, and saved as:
> - `cleaned_TCS_stock_history.csv`
> - `cleaned_TCS_stock_action.csv`
> - `cleaned_TCS_stock_info.csv`

---

## Feature Engineering

- Daily & Cumulative Returns
- Technical indicators: `MACD`, `Signal Line`, `RSI`
- Lag Features: `Lag_1`, `Lag_2`
- Rolling Stats: `Rolling_Mean_7`, `Rolling_Std_7`
- 52-week High (based on 252 trading days)

---

## Exploratory Data Analysis

- Volume and price trends by month, day, and weekday
- Rolling averages (MA20/MA50)
- RSI and MACD crossovers
- Cumulative returns and daily return distributions
- Correlation heatmaps
- Events analysis: dividends, splits

---

## Models Used

| Model               | Type             | Purpose                      |
|--------------------|------------------|-------------------------------|
| Linear Regression   | Classical ML     | Baseline trend fitting        |
| Random Forest       | Ensemble ML      | Captures non-linear patterns |
| XGBoost             | Boosted Trees    | Gradient-based boosting       |
| LSTM                | Deep Learning    | Sequence-aware forecasting    |
| Prophet             | Time Series      | Long-term trend/seasonality   |

📈 Each model’s predictions were compared against actual values using RMSE and R² score.

---

## Model Results Summary
---
![Screenshot 2025-05-18 034743](https://github.com/user-attachments/assets/9e30cf2b-865c-4b76-aa72-acb377d8797f)

---
| Model             | RMSE     | R² Score   |
|------------------|----------|------------|
| Linear Regression| 14.71    | ~0.999     |
| Random Forest    | 990.85   | —          |
| XGBoost          | 1067.58  | -2.22      |
| LSTM             | 246.29   | 0.827      |

---

## Dashboard (📁 `dashboard.py`)

An interactive Streamlit app with:

- Filters (Day, Month, Quarter, Year)
- Metrics for average highs/lows, total volume, open/close
- Charts:
  - Quarterly & monthly aggregates
  - Volume by month
  - Open vs Close
  - 52W High/Lows
  - Time-based trends

> Deploy this locally with:
streamlit run dashboard.py

===

# TCS Stock Price Prediction Dashboard live

This interactive Streamlit app forecasts TCS stock prices using machine learning models trained on historical data. The dashboard supports multiple timeframes and model types, offering flexibility for both short-term and long-term analysis.

---

## Features
- Price prediction visualization with actual vs. predicted comparison.
- Technical indicator overlays like MA20, MA50, RSI, and MACD.
- Buy/Sell signal generation using EMA crossover logic.
- Error metrics (MAE, RMSE, R², Sharpe Ratio) displayed for easy model evaluation.
- Tabs for analysis: Navigate through price prediction, technicals, sentiment, and macro factors for deeper insights.

### Model Selection
- Toggle between **Random Forest**, **XGBoost**, and **LSTM** models.
- Evaluate predictions based on:
  - **MAE** (Mean Absolute Error)
  - **RMSE** (Root Mean Squared Error)
  - **R² Score**
  - **Sharpe Ratio**

### Timeframe Support
Choose from multiple forecasting intervals:
- `1D (1-min)`
- `5D (30-min)`
- `1M (daily)`
- `6M (daily)`
- `1Y (daily)`
- `5Y (weekly)`

### Visualization
- Interactive candlestick charts for actual vs. predicted prices.
- Moving averages (MA20, MA50) overlays.
- Buy/Sell signal generation using **EMA crossover**.
- Dynamic date selection and plotting based on user input.

---

## Tabs in Dashboard
- **Price Prediction**: View forecast charts and metrics.
- **Technical Indicators**: RSI, MACD, Bollinger Bands, etc.
- **News & Sentiment**: (Future scope for integration)
- **Macro Indicators**: Add contextual macroeconomic signals.

---

## Tech Stack
- **Python**
- **Streamlit**
- **Pandas**, **NumPy**
- **Plotly**, **Matplotlib**
- **Scikit-learn**, **XGBoost**
- **Keras/TensorFlow** (for LSTM)

---

## 🧩 How to Run
streamlit run app.py
