# energy_forecast
task: ashrae energy forecasting

Data from https://www.kaggle.com/c/ashrae-energy-prediction. 

Aim : 'meter_reading' prediction for different 'building_id' present at different 'site_id' for different 'meter' types. 

Additional data present is weather data (e.g. temperature, wind speed etc)  as well as building data (e.g area, use of building etc)

Preprocessing includes imputing missing data as well as removing outliers/anomalies that affect overall label value or trends in the case of time series forecasting. In our case, this would amount to figuring out anomalies in building data or site data or meter data or weather data that has a major effect in overall trend for our label.

Modelling: 
- LightGBM
- ARIMA
- Transformer Based Model

