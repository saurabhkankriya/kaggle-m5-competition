### To do:
1. Create the loss function
2. helper function that reduces the size of the dataframes
3. EDA in separate notebook
4. naive forecasts
5. helper function that compress submission csv file size


# Modelling
* Time Series Models
* Machine Learning models
* Deep Learning


As I know some of you are using Prophet for time series forecasting, here are two lifehacks:

If you only want to have your forecast and don't need the lower and upper bounds, you can set the uncertainty_samples parameter to 0. By default it is set to 1000 to provide the bounds by using Monte Carlo simulations. Setting it to 0, saves you up to 94% of runtime (so was in my case) and provides the exact same forecast results. You can find more information here: https://github.com/facebook/prophet/issues/1082

When applying the make_future_dataframe method and then using the predict method on it, also all data points of the past are predicted. As they might not be used, only predict the future (delete the past from the future dataframe). By applying both hacks, you can save around 96% of runtime.

~ Mathias
