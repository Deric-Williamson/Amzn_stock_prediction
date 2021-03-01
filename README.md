# Amzn_stock_prediction
 Deric Williamson

## Business Case
An investment company wants to start looking into AI to predict the markets.  As a Data Scientist, I have been hired to look at Amazon stocks to predict when to invest the company’s money into the stock. If this prediction model works, the company will expand their AI efforts to other stock markets.


## Method
In place of using a time series model, I decided to use a more unconventional route and implemented a **classification model** instead. 

My model is focused on predicting any **4 percent price increase within a five-day range.**


## Data 
The data was collected from [AlphaVantage.co](https://www.alphavantage.co/) api. 

|data features:|
|--------------|
|  open price  |
|  high price  |
|  low price   |
|  close price |
|  volume      |

I will be using the last 1500 market days (roughly 6 years)  


|   Days not to invest| Days to Invest |
|---------------------|----------------|
|   1053              |        447     | 
   
In the last six years, The amazon sees a 4 percent price change within 5 days about a third of the time.  
Note, the days that sees a 4 percent price change within 5 days are typically grouped  


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
<img src="/images/feature_importances.PNG" width = 25%/> 

Interestingly my model did not make use of the stochastic or the relative strength index(RSI) techinical Indicators or the Open and Low prices.


### Gradient Boosting
<img src="/images/classification_report.PNG" width = 50%/>  

Precision = .84  
Recall = .21  
  
Precision is more important in this model, It signifies the ratio between good investments to bad.  
Recall is still important in this model, It signifies the ratio between found to loss inventing opportunities  


|   All X's and Y's                                  |               Test X's and Y's                     |
|----------------------------------------------------| ---------------------------------------------------|
|<img src="/images/confusion_matrix_full.PNG"/>      |  <img src="/images/confusion_matrix_test.PNG"/>    | 





## Misclassified Data
These four data points represents the bad investment opportunites that my model suggest will go up four percent.
<img src="/images/false-positives.PNG" width = 100%/> 

* One point did go up to 3.975 percent
* The rest was during Pandemic times, but other than that, I am unsure why it couldve failed.

## Predictive Function
| Invest                                             |               Don't Invest                         |
|----------------------------------------------------| ---------------------------------------------------|
|<img src="/images/amzn_predict1.PNG"/>              |  <img src="/images/amzn_predict2.PNG"/>| 


## Recommendations
* I would recommend the investment company to continue to expand their AI efforts to other stock markets.

* When focusing on technical indicators, I would suggest focusing on:  Average True Range (ATR), Simple Moving Average (SMA), Average Directional Index (ADX), Rate-of-change (ROC);    With less focus on: Stochastic and Relative Strength Index (RSI) indicators.

* Having a sell point barely lower than 4 percent to catch some false positives. 


## Future Works
* My initial XGB models yielded decent stats, so I would like to test the XGB model as a best estimator in place of the decision tree.

* Focus on adding more technical indicators.

* Explore other stock markets to be able to find at least 5-10 investing opportunities a week.




