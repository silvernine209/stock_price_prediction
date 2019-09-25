# Using News to Predict Stock Movements 
This project contains my two submissions for Kaggle competition : [Two Sigma: Using News to Predict Stock Movements](https://www.kaggle.com/c/two-sigma-financial-news).  
Achieved top 2% in leaderboard.

* Refer to "Featured Notebooks/Analysis/Deliverables" section for fully executed Jupyter Notebooks

#### -- Project Status: [Completed]

## Project Intro/Objective
The purpose of this project is predict a signed confidence value that's correlated with stock price movement.  
Therefore, predicted signed confidence value can be used by the competition host to make better decisions on stock trading.

### Partner
* [Two Sigma](https://www.twosigma.com/) is hosting this competition through [Kaggle](https://www.kaggle.com/c/two-sigma-financial-news#description).
* In this competition, market data is provided by Intrinio and news data is provided by Thomson Reuters.

### Methods Used
* Exploratory Data Analysis
* Deep Learning
* Data Visualization
* Predictive Modeling


### Technologies
* Python
* Jupyter Notebook
* Pandas
* Numpy
* Matplotlib
* Seaborn
* etc. 

## Project Description

You can find base code in .ipynb format and its executed output by clickin "- executed" link.
Data used in this executions are only accessible through Kaggle's kernel, which is a virtual environment within server for copyrights reasons. Therefore, it is not possible to replicate this work.  
To learn more about the data, you can view it [here](https://www.kaggle.com/c/two-sigma-financial-news/data).  














# Chicago Crime Rate Prediction
I built a linear regression model (ElasticNet) to predict Chicago's daily crime rate by web scraping 10 years worth of various weather data. Then I added more data (total ridership and unemployment rate) on top of performing feature engineering.

## Project Intro/Objective
The City of Chicago spends more than $4 million dollars on the Chicago Police Department **DAILY**, which is 38% of their budget. Accurate,or any, prediction on daily crime rate can assist the City of Chicago with better budgeting for efficient use of resources.

## Methods Used
* Linear Regression (ElasticNet)
* Web Scraping
* Data Preprocessing
* Feature Engineering
* Data Visualization
* etc.

## Notable Technologies Used
* Python 3, Jupyter Notebook
* Pandas, Numpy, Matplotlib, Seaborn
* Selenium, BeautifulSoup
* Scikit-learn
* RandomizedSearchCV
* etc. 

## Feature Engineering
Project initially started with only using weather data (temperature, humidity, pressure, wind condition, and weather conditions) because I had a hypothesis that weather is highly correlated to crime rate in general. Then, poor model performance guided me to add more features (total rides per day and unemployment rates). My most time was spent on taking an iterative approach to feature engineering.

* **Temperature & Its Moving Avg**- high/low of the day. Hotter it is, people are more hot-tempered
* **Humidity** - How uncomfortable are you?
* **Barometer** - Might affect the mood?
* **Wind Speed** - Less crime in windy days
* **Weather Description** - Clear/Foggy/Overcast/etc..
* **Day of Week** - (Mon - Sun) More crimes on weekends?
* **Month of the Year** - Some crimes are seasonal (pick-pocketing in NYC during Christmas and such)
* **Total Rideds** - Bus/Subway/etc. More people = more crime
* **Unemployment Rate** - Some resort to crimes

## Model 
Lasso model was used as a baseline model with only weather data (all numerical features). As more features were added (day of the week, month of the year, weather description, and etc.), I assumed complex interactions among features since predicting a crime rate is a very complex task such as predicting stock price. Therefore, I moved onto ElasticNet model after applying 2nd degree polynomial features to existing features, which resulted in 595 features. ElasticNet was a perfect model for this case since RandomizedSearchCV was utilized on training dataset, this was very important as it applied automatic selection of hyper-parameter and feature selection on top of performing cross validation on the training data.

Below is R^2 score of various combination of models and features.
![models](img/models.jpg)

## Result 
Below is actual vs predicted and residual plot of ElasticNet model that had the best performance. Its MAE (Mean Absolute Error) score was 50, which means my model is able to predict Chicago's crime rate with +- 50 crimes per day. Coefficients from ElasticNet picked up temperature, total ridership, and unemployment as the most important features that affect crime rate.
![results](img/result.JPG)

## Conclusion
This project was all about identifying the right dataset to take advantage of highly explainable linear regression models. Even though my model was able to perform very well with R^2 score of 0.82 on the test set, further investigation is needed to validate the process and measures taken in this project. For future expansion, I would like to add more data such as average income, population density, and etc.



## Featured Notebooks/Analysis/Deliverables
* [NN Model.ipynb](https://github.com/silvernine209/stock_price_prediction/blob/master/NN%20Model.ipynb)  
* [NN Model.ipynb - executed](https://www.kaggle.com/silvernine/very-simple-nn-model-market-data-only/notebook)  
* [XGBoost.ipynb](https://github.com/silvernine209/stock_price_prediction/blob/master/NN%20Model.ipynb)  
* [XGBoost.ipynb - executed](https://www.kaggle.com/silvernine/lb-0-53-market-news-xgboost-for-beginners)



