# Pharmaceutical-Sales-prediction-across-multiple-stores

The main objective is to build an end-to-end product that forecast sales in all
Rossmann Pharmaceuticals stores across several cities.

## Data

* Data is found in https://www.kaggle.com/c/rossmann-store-sales/data 
* The data used contains 3 different informations which are the store information and the sales
information for each store throughout the data collected years and additional test csv file to test the output.

### Columns

* Sales: the turnover for any given day (target variable).
* Customers: the number of customers on a given day.
* Open: an indicator for whether the store was open: 0 = closed, 1 = open.
* Promo: indicates whether a store is running a promo on that day.
* StateHoliday: indicates a state holiday. Normally all stores, with few exceptions, are closed on state holidays.
* SchoolHoliday: indicates if the (Store, Date) was affected by the closure of public schools.
* Store: a unique Id for each store
* StoreType: differentiates between 4 different store models: a, b, c, d
* Assortment: describes an assortment level: a = basic, b = extra, c = extended
* CompetitionDistance: distance in meters to the nearest competitor store
* CompetitionOpenSince[Month/Year]: gives the approximate year and month of the time the nearest competitor was opened
* Promo2: Promo2 is a continuing a promotion for some -stores: 0 = store is not participating, 1 = store is participating
* Promo2Since[Year/Week]: describes the year and calendar week when the store started participating in Promo2
* PromoInterval: describes the consecutive intervals Promo2 is started, naming the months the promotion is started.


## Models
1. facebook prophet model used for forcasting 
2. Regression model 
3. Random Forest 
4. Xgboost
5. Deep learning using LSTM

### Models output

#### Linear Regression

##### Hyperparameters values tuned

		fit_intercept=True,
		normalize=True,
		n_jobs=None
		Metrics values results
		
##### Metrics

		Mean squared error on validation data = 0.118
		Mean absolute error on validation data = 0.253
		Mean R2 score on validation data = 0.989


#### Random Forest

##### Hyperparameters values tuned

		n_estimators = 12
		Metrics values results
		
##### Metrics

		Mean squared error on validation data = 0.0184
		Mean absolute error on validation data = 0.0765
		Mean R2 score on validation data = 0.998

		
#### Xgboost

##### Hyperparameters values tuned

		alpha = 11
		learning_rate = 0.09
		random_state = 4

##### Metrics

		Mean absolute error on validation data = 0.1839
		Mean squared error on validation data = 0.0687
		Mean R2 score on validation data = 0.993
		
#### Deep Learning LSTM

##### Hyperparameters values tuned

		LSTM = 10
		DNN layer = 2
		Epoch = 2
##### Metrics

		Mean squared error on validation data = 0.0320
		Mean squared error on training data = 0.0380	
		
## Web App

* Streamlit is used to build the web app. 
* A prediction csv file of the test.csv data set is saved to displace as an output on the webapp. 


## Conclusion 
* The quantity of clients is significantly connected with sales.
* During school holidays, more stores are open than during state holidays.
* Promotions result in an increase in both sales and customers for all stores.
* Stores that are open during the school holidays generate more sales than on
other days.
* A is the most popular storetype.
* The LSTM Model can do give a better prediction prefromance if layers are increased and training Epochs are increase, 
but for this expriement the training epoch and hiddlen layers are less. 
* The best Model from the Metrics out put is Random forest. 
