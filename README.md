## Business_Applications 
## Capstone Initiation - Home Credit Default Risk Prediction 
### Business Description
Home Credit is an international consumer finance provider focused on responsible lending primarily to people with little or no credit history. As the company provides financial support for home purchasers the company makes sure that they are lending the money to the right and responsible clients, who have the ability to repay the loan amount. Home Credit wants to use various statistical and predictive analysis methods on the requester data collected previously and current data to unearth the credibility of a requester by predicting whether they would be able to repay the entire loan with interest in due course of time i.e. predict whether an applicant is likely to default. 

### Analytical Approach
#### 1. Understanding Data sets provided 
In this project, there are 8 CSV files that we have used. 
application_train.csv - data set for training model
application_test.csv - data set for testing 
bureau.csv
bureau_balance.csv
credit_card_balance.csv
installments_payments.csv
POS_CASH_balance.csv
previous_application.csv

The target variable identified here is whether the requester will default or not. A simple binary variable Target with values 1 (if the requester has had difficulties in payment previously) and 0 (for all other situations) assessing closely the credibility of a requester can be statistically analyzed and a predictive model can be developed through classification algorithms. 

#### 2. Exploratory Data Analysis - 
In the EDA part of the project, different predictors are correlated with the target variables to understand the relationships through various visuals. 
Furthermore, the imbalance in the data set has been explored along with the percentage of null values present in the predictor columns. 

#### 3. Data Cleaning and Profiling Methods
In the data cleaning phase of the project, the data sets have been merged based on the common key, variables with more than 30% null values have been removed, and based on the correlation output, strong features have been selected.

#### 4. Data Modelling
In the data modeling phase, supervised classification methods, the project includes XgBoost, logistic regression, Naive Bayes, and random forest model. 
The project further explores hyperparameter tuning to make the models more robust and efficient. 
It is observed that the XgBoost model has better performance in comparison to other models. 

#### 5. Business Valuation
Based on the XgBoost models output and selection of important features, the project concludes that top predictors classify applicants to identify whether they will default or not, these features should be analyzed in more depth before offering loans to any applicant. 
The top features are 
1. EXT_SOURCE_3: Normalized score from the external data source
2. EXT_SOURCE_2: Normalized score from the external data source
3. DAYS_BIRTH: Client's age in days at the time of application
4. DAYS_ID_PUBLISH: How many days before the application did the client change the identity document?
5. DAYS_REGISTRATION: How many days before the application did the client change their registration?
6. DAYS_EMPLOYED: How many days before the application the person started their current employment
7. DAYS_LAST_PHONE_CHANGE: Number of days since the client last changed their phone number
8. AMT_ANNUITY: Loan annuity
9. SK_ID_CURR: The ID of the loan in our sample
10. AMT_CREDIT: Final credit amount on the previous application
