# TCS Stock Price Prediction App

This Streamlit application provides stock price prediction for TCS (Tata Consultancy Services) using pre-trained machine learning models. The app supports multiple timeframes and model types, and includes technical indicators, news sentiment analysis, and macroeconomic indicators.

## Features

- **Multiple Timeframes**: 1D (1-min), 5D (30-min), 1M (daily), 6M (daily), 1Y (daily), and 5Y (weekly)
- **Multiple Models**: RandomForest, XGBoost, and LSTM
- **Interactive Charts**: Candlestick charts with technical indicators
- **Technical Analysis**: MA20, MA50, RSI, MACD
- **Buy/Sell Signals**: Based on EMA crossover strategy
- **News Sentiment Analysis**: Analysis of TCS news headlines
- **Macroeconomic Indicators**: NIFTY50 and USD/INR trends

## Project Structure

```
├── app.py                  # Main Streamlit application
├── utils/
│   ├── model_loader.py     # Model loading utilities
│   ├── indicators.py       # Technical indicator calculations
│   ├── plotter.py          # Visualization functions
│   └── sentiment.py        # News sentiment analysis
├── data/
│   ├── processed/          # Processed data files
│   ├── nifty50.csv         # NIFTY50 data
│   ├── usdinr.csv          # USD/INR exchange rate data
│   └── tcs_news.csv        # TCS news headlines
└── models/                 # Pre-trained models
```

## Installation

1. Clone the repository or download the files
2. Install the required dependencies:

```bash
pip install -r requirements.txt
```

3. Run the Streamlit app:

```bash
streamlit run app.py
```

## Usage

1. Select a timeframe from the sidebar
2. Choose a model type (RandomForest, XGBoost, or LSTM)
3. Select an end date for the prediction
4. Click the "Predict" button
5. View the results in the different tabs:
   - Price Prediction
   - Technical Indicators
   - News & Sentiment
   - Macro Indicators

## Models

- **Short-term Prediction**: RandomForest and XGBoost models for 1D, 5D, 1M, and 6M timeframes
- **Long-term Prediction**: LSTM models for 1Y and 5Y timeframes

## Notes

- The app automatically selects the appropriate model based on the timeframe
- For best results, ensure all data files and models are available in their respective directories
- The sentiment analysis requires TextBlob or NLTK's VADER, which will be installed with the requirements