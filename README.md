# energy_forecast
task: ashrae energy forecasting

Data from https://www.kaggle.com/c/ashrae-energy-prediction. 

Aim : 'meter_reading' prediction for different 'building_id' present at different 'site_id' for different 'meter' types. 

Additional data present is weather data (e.g. temperature, wind speed, etc)  as well as building data (e.g area, use of building, etc)

Preprocessing includes imputing missing data as well as removing outliers/anomalies that affect overall label value or trends in the case of time series forecasting. In our case, this would amount to figuring out anomalies in building data or site data or meter data or weather data that has a major effect in overall trend for our label.

Final modelling is done on a subset of the dataset post processing and evaluated on RMSLE.

Feature engineering methods:
- removing some features and evaluating models
- utilizing all features
- using lag values as well along with features
- normalizing time features such as month, week and day to a sin/cos feature 

Final task is evaluating on the holdout 12th month of the year

Modelling: 
- LightGBM -> using cross validation and evaluated feature imporatance -> 0.57 score when using lag values
- ARIMA -> used the package pmdarima; final score 6.26
- Transformer Based Model -> used pytorch-forecasting ; final score -> 0.77


Result: for time series, gradient boosting trees present better results compared to other methods in terms of evaluation as well as evaluation time. This is also collaborated with research data on time series modelling. LightGBM is also much faster thatn XGBoost. Additionally, while transformer or other deep learning methods might be better, at present they are not time efficient.
