# HydroGAPML


## 1-day ahead forecast

For each station a  RandomForest or GradientBoosting regressor model is trained, using previous days lags.


### Usage




```python
import joblib

station_model_name = "station_518.pkl"
model = joblib.load( station_model_name ) 
test_df  = pd.DataFrame( [{
    "P_lag_time_1": 2.372996,
    "P_lag_time_2": 9.947697,
    "P_lag_time_3": 0.009867,
    "Q_lag_time_1": 68.500000,
    "Q_lag_time_2": 79.199997,
    "Q_lag_time_3": 76.800003,
    
}])

model.predict(test_df) # array([72.47600025])

``` 



## 2-weeks ahead forecast

For each station a  RandomForest or GradientBoosting regressor model is trained, using previous days lags.
Here, the model is trained to predict the next 14 days

### Example forecst



```python

import joblib

station_model_name = "mo_station_518.pkl"
mo_regressor = joblib.load( station_model_name ) 

test_df  = pd.DataFrame( [{
    "P_lag_time_1": 2.372996,
    "P_lag_time_2": 9.947697,
    "P_lag_time_3": 0.009867,
    "Q_lag_time_1": 68.500000,
    "Q_lag_time_2": 79.199997,
    "Q_lag_time_3": 76.800003,
    
}])

mo_regressor.predict(test_df) 
# array([[ 72.47,  889.4 ,  908.11,  955.46,  973.27, 1036.01, 1041.62,
#        1069.79, 1088.86, 1111.55, 1162.48, 1178.34, 1174.13, 1195.35]])
``` 