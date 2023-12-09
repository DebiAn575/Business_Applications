## MAVERIK STORE DAILY SALES FORECAST
### Table of Contents
1. [Business Description](#1-business-description)
2. [Analytical Approach](#2-analytical-approach)
   1. [Understanding Data sets provided](#21-understanding-data-sets-provided)
   2. [Exploratory Data Analysis](#22-exploratory-data-analysis)
   3. [Data Cleaning and Profiling Methods](#23-data-cleaning-and-profiling-methods)
   4. [Data Modelling](#24-data-modelling)
   5. [Data Modeling - Debayan Contribution](#25-data-modeling-debayan-contribution)
3. [Business Valuation](#3-business-valuation)
4. [Challenges](#4-challenges)
5. [Learning Outcomes](#5-learning-outcomes)

### 1. Business Description
Maverik is a large convenience store chain with over 400 locations in the western United States. It recently acquired Kum & Go, doubling its store count. Maverik is multiplying and plans to open 30 new stores each year. This makes planning new stores a crucial part of the business. Maverik wants to use various statistical and predictive analysis methods on active stores' historical sales data from 2021 till 2023 to forecast the daily sales of 4 category items, namely 'daily_yoy_ndt.total_inside_sales', 'daily_yoy_ndt.total_food_service', 'diesel,' 'unleaded', for the upcoming year, for any new store they open.
The organization analyzes its time-series data to analyze and predict the daily sales of new Maverik stores. It holds the sales data from other stores from 2021 until August 2023 of the four categorical items crucial to assessing a store's sales performance. Maverik is also parallelly analyzing and correlating the sales data with qualitative data representing various items that store stock and sale. Does having a specific item in the store increase overall sales? Are two or more items in the store highly correlating and can be a factor for the causality of purchase? Does the seasonality affect the stores' overall sale or sale of a specific item? How does gas price fluctuation impact on a store's overall sales? These are the few questions that Maverik may want to know before opening a new store during a specific time of the year. To statistically analyze the available data yield answers and forecast daily sales records, Maverik can use statistical tools like R, perform extensive exploratory data analysis data preprocessing, and develop Time-series models to predict the outcome.
The solution, forecasting sales for the next financial year for the new store, is crucial for Maverik. Using statistical analysis, Maverik can deliver a running total of daily sales numbers in dollars; using the daily sales and total overall forecasted sales amount, Maverik can perform revenue forecasting and budgeting for the new stores. They can develop an expense projection plan, work on cash-flow and gross margin analyses, and obtain operating profit margins. These metrics will help them determine the Return on Investments for the newly opened stores.
The Business data scientist team members will be working on the data provided by Maverik data management teams to perform the analysis and provide the numbers as the solution, which are the daily sale value of the four products (target variables) 'daily_yoy_ndt.total_inside_sales', 'daily_yoy_ndt.total_food_service', 'diesel,' 'unleaded.' Business data analysts or data scientists can perform exploratory data analysis, to begin with and divide the data first into train and test sets. They can develop multiple predictive models and work with the train and test set to evaluate which model has higher RMSE, MAE, MAPE; generally, they can consider the Receiver operating characteristic to determine the appropriate model to move forward with.
This project will run for 14 weeks, starting in September and ending in early December. The actionable business insights will be conveyed to the management for model buy-out through a pitch presentation.
 

### 2. Analytical Approach
### 2.1 Understanding Data sets provided 
In this project, there are 2 CSV files, one with timeseries data related to the 4 target variables and one with the qualitative data of 38 stores, that we have used. 
The target variables are total_inside_sales, total_food_sales, diesel and unleaded. Our approach is to use both historically sales data of the 4 target variables and the qualitative data of the stores and engineer a daily sales forecasting model for next one year that would help Maverik with investigating ROI and budgeting for the next year. We use predictive timeseries algorithms to design the model appropriately forecasting sales and minimizing the forecast percentage error in comparisons to Maverik's own naive model. 

### 2.2 Exploratory Data Analysis - 
In the EDA phase we have explored trend seasonality in the given sales data of the 4 target variables and tried to obtain correlation information about the different qualitative data and the target variables. 
We have observed that there are although no null/blank values in the data but the values which are not available has been repalced with "None". 
The trend and seasonality shows that the sale of items is high during the summer months while gradually reduces by end of year before picking up during the beginning of new year. 
It is also observed that the target variable also influence each others sales over the years. 

### 2.3 Data Cleaning and Profiling Methods
In the data cleaning phase of the project, the data sets have been merged based on the common key, a feature is engineered as the tenure date relaetd to the opening date of the stores, and based on the correlation output, strong features have been selected and qualitative data has been hot-encoded. 

### 2.4 Data Modelling
In the data modeling phase, Five models were developed to leverage Maverik’s historical sales data: Vector AutoRegressive Model, Prophet, Support Vector Regression, Extreme Gradient Boosting and ARIMA/ETS ensemble. Each model is tuned to minimize RMSE, which is the metric used to select the final model.
The project further explores hyperparameter tuning to make the models more robust and efficient. 
It is observed that the ARIMA/ETS has better performance in comparison to other models. 

### 2.5 Data Modeling - Debayan Contribution
I used exploratory data analysis to identify trend and seasonality in the timeseries data and performed correlation matrix of qualitative data to identify the important predictors. 
It was interesting to know that the since we had historic sales data of the stores, which automatically incorporated the qualittative data into the sales data it was presummable to use only the quantitatve data to start with a basic ARIMA model for the sales forecast. 
I have used Support Vector Regressor algorithm to develop a model to forecast the sales for the target variables. The Model uses scaled quantitative data and has a RSME value of 
- rmse_inside_sales = 0.3448517
- rmse_food_service = 0.2782577
- rmse_diesel = 0.567455
- rmse_unleaded = 0.8332988
  
### 3. Business Valuation
Based on the ARIMA/ETS models output and selection of important features, the project concludes that the total sales for each of target variables for the next one year is as follows for one of the Maverik stores 
- inside_sales = $1,227,062
- food_service = $338,871
- diesel = $503,891
- unleaded = $983,141
- total_sales = $3,052,965

We also observed some qualitative predictors affecting sales more than the others which should be further studied in depth to increase sales or make budget related decisions

FACTORS AFFECTING STORE BUSINESS
- Diesel Sales
- Inside Sales
- Parking Space
- Toilet Count
- Population within 5-mile radius
- Number of individuals in workplace within 5-mile radius 


### 4.  Challenges 
The challenge in the project was to run big models on limited hardware resources, the models took a lot of time to run and produce results. 
Standardized Data Sets with limited number of rows. The dataset was already standardized hence the resulted forecast cannot be considered exact they can be inflated. 
Multivariate Multi-target Analysis. The modeling for each of the target variables was tedious as individual models had to be created to make sales forecast. 
Insufficient historical data to accurately calculate annual seasonality. We obserevd seasonality on weekly, monthly and yearly basis in our EDA and since the data was only 3 years reintroducing seasonality on forecasted data was troublesome. 
Unavailability of precise Geographical data. Since we had to predict the sales of a new store, geographic data of stores in that area would have been help for the project. 
Time Constraints. 
Since there was no direct communication with the sponsors, going back and forth with questions about the data provided was not possible which was possible set back. 

### 5. Learning Outcomes
The major learning outcome of the capstone project is that a number of timeseries models were explored and the working principles of these models we were able to learn. The project also gives ideas about different stages and steps of exploratory data analysis and takes a deep dive into the usage of Python/R for predictive forecasting projects. As this was a collaborative project, learning group communication, professional use of a notebook, and presentation skills were also tested and honed. 
