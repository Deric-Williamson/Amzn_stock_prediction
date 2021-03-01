# Amzn_stock_prediction
* Deric Williamson

## Business Case
An investment company wants to start looking into AI to predict the markets.  As a Data Scientist, I have been hired to look at Amazon stocks to predict when to invest the company’s money into the stock. If this prediction model works, the company will expand their AI efforts to other stock markets.


## Method
In place of using a time series model, I decided to use a more unconventional route and implemented a classification model instead. 

My model is focused on predicting any 4 percent price increase within a five-day range.


## Data 
https://www.alphavantage.co/

the data features:
* open price
* high price
* low price 
* close price
* volume

## Column Engineering
I have engineered technical indicators to help with the predictions.  
These included: 
* Simple Moving Average (SMA)
* Stochastic
* Relative Strength Index (RSI)
* Rate-of-Change (ROC)
* Average True Range (ATR)
* Average Directional Index (ADX)

## Model
Knn and svc models did poorly on the base modeling process.  
Decision Tree and XGB models both had decent starting stats.  
My Efforts had been spent on the Decision Tree Classifier to use as a best estimator to the Gradient Boosting model.

### Decision Tree Classifier


