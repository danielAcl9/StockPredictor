# STOCK PRICE PREDICTION - S\&P GLOBAL

This project addresses the task of predicting stock prices by combining historical price data with market news. The objective is to develop a predictive model that demonstrates good baseline performance, while also exploring the impact of integrating heterogeneous data sources such as financial time series and textual information.

---

## Project Structure

* **EDA (Exploratory Data Analysis)**
  Initial exploration of the datasets to understand stock price behavior, distribution of returns, and volatility patterns.

* **Feature Engineering**
  Creation of price-based features such as returns, moving averages, volatility, and lagged prices, along with simple news-derived features.

* **Modeling**
  Training and evaluation of baseline and advanced models to compare performance and understand predictive drivers.

* **Evaluation**
  Quantitative and visual assessment of model accuracy, error metrics, and limitations.

* **Future Improvements**
  Suggestions to extend the project with richer features and advanced modeling techniques.

---

## Dataset Description

### price.csv

Historical stock price and volume data.

* date: Trading date
* ticker: Stock ticker symbol
* open: Opening price
* high: Highest price of the day
* low: Lowest price of the day
* close: Closing price
* volume: Number of shares traded

### news.csv

Market news associated with stock tickers.

* datetime: Publication timestamp
* ticker: Stock ticker symbol
* headline: Concise news title
* summary: Short description of the article

---

## Exploratory Data Analysis (EDA)

### Steps performed

- **Price Data (price.csv):**
    - Reviewed key columns (date, open, high, low, close, volume).
    - Checked for duplicates and missing values (none were found).
    - Created exploratory plots such as stock prices over time.

- **News Data (news.csv):**
    - Reviewed columns (datetime, headline, summary).
    - Counted number of news articles per day.
    - Missing values were found in some rows.

- **Merging:**
    - Price and news datasets were merged on date.
    - When multiple news articles were published on the same day, they were aggregated.

### Key insights
A Stock Closing Price Over Time chart revealed the following behavior: From November 2023 to early January 2024, the stock price rose sharply, peaking close to 590. In mid-January, there was a sudden drop, followed by abrupt jumps later in the month. Since February, the price stabilized in the 400–450 range.
The chart indicates strong early growth, a massive drop, high volatility, and sharp movements that suggest potential market events requiring further review.
---

## Feature Engineering

* **Daily Return**: Percentage change in closing price from the previous day.
* **Moving Averages (3-day and 7-day)**: Capture short- and medium-term trends.
* **Volatility (7-day rolling)**: Identifies periods of strong price fluctuations versus stability.
* **Lag Features**: Closing prices from previous 1 and 3 days to capture momentum effects.
* **News Count**: Aggregated number of news articles per day, aligned with price data.

---

## Modeling

Two models were implemented for comparison:

1. **Baseline Linear Regression**

   - RMSE: 13.42
   - MAE: 4.81
   - The linear model provides a relatively low error. This means that simple linear relationships based on historical prices are effective for this dataset.

2. **XGBoost Regressor (with news_count feature)**

   - RMSE: 25.03
   - MAE: 17.61
   - XGBoost model is much worse than the baseline. This shows that for this case, adding the news features introduces noise rather helps the prediction.

The linear regression outperformed the XGBoost model. The simple news_count feature did not improve predictions, suggesting that more information is needed to explain price movements. Price-based features carried most of the predictive signal.

---

## Results

The Linear Regression model successfully followed the overall price trend, performing well during stable periods. However, it struggled to capture sudden, sharp changes in price (e.g., around the 100-time unit mark). Despite these limitations, the baseline model demonstrated that even simple price-derived features can achieve reasonable predictive accuracy.

The results show that a simple linear regression outperforms a more complex XGBoost model in this dataset. While errors remain significant in some cases, the approach demonstrates how integrating market news with price data can help capture stock dynamics.