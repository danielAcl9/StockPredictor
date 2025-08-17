# STOCK PRICE PREDICTION - S&P GLOBAL

The task is to build a model to predict stock prices using the provided datasets. This classic challenge in data science requires to leverage historical data and associated market news.

## Feature Descriptions

### news.csv
#### Historical News
This dataset provides real-time news articles related to specific trading tickers. Each news article includes:

- **datetime**: Timestamp of the news article's publication.
- **ticker**: Stock ticker symbol associated with the news.
- **headline**: Concise summary of the news article.
- **summary**: Summarization of the article content.

### price.csv
#### Historical Price Data
This dataset contains historical price and volume data for various trading tickers. For each ticker, the following information is provided:

- **date**: Trading date.
- **ticker**: Stock ticker symbol.
- **open**: Opening price of the stock on the given date.
- **high**: Highest price reached by the stock during the trading day.
- **low**: Lowest price reached by the stock during the trading day.   
- **close**: Closing price of the stock at the end of the trading day.
- **volume**: Total number of shares traded on the given date.

### Problem Description:
The task involves predicting stock prices based on historical data and corresponding market news. You are required to develop a predictive model from scratch that demonstrates robust performance on unseen data. This assignment will help showcase your modeling skills and your ability to synthesize different data sources in stock price prediction.



Granularidad = nivel de detalle.

Se necesita porque precios son diarios, noticias son múltiples → hay que unificarlas.

Esto se alinea con la prueba porque es el paso clave de “sintetizar datos heterogéneos”.