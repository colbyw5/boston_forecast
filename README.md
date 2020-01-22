### Forecasting Temperature in Boston, MA

Objective: the intention of this repository is implement an end-to-end time series analysis and forecast.  We will visualize our data, assess the error-trend-seaonal decomposition, and test for stationarity.  We will then fit two models on a training data set, while holding our the most recent year of data for model evaluations: and ARIMA model and a deep learning method (LSTM).  We will assess model fit visually and using mean-squared error and mean absolute error.  Finally, using our best performing model, we will retrain the model on the full data set and forecast temperature for 2020.

Language: Python 3.7.5

Repository Guide

- code
    - clean: this directory contians a jupyter notebook used to clearn the Boston ISD data file from the raw data download.
    - model: this directory contains the jupyter notebook where the data was explored, the models were fit and evaluated, and the forecast for 2020 was generated
- visualizations: this directory contains plots used during exploratory analy
- data
    - raw: original ISD data file for Boston, MA
    - clean: data file generated via the clean data notebook
- documentation: technical documents detailing ISD data collection process and structure of data files

Data: The data used in this project is from the NOAA Integrated Surface Data (ISD) availble here: .  The ISD data contains numerous historical features captured from ISD stations, though in this project we focused on monthly temperature from 1989-2019.

![Monthly Temperature in Boston 1989-2019](https://github.com/colbyw5/boston_forecast/blob/master/visualizations/Boston_Temp.png)

Method: Based on exploratory analyses, we chose to forecast temperature in Boston using SARIMA and LSTM.  SARMIA was used to account for the obvious seasonality of the data, with parameters chosen via grid search.  We also used LSTM to compare the commonly used ARIMA modelling framework to more recent advancements in deep learning for time series analysis.  A plot of the 12-month rolling mean and standard deviation is below.

![Monthly Temperature in Boston 1989-2019: 12-month rolling mean and std](https://github.com/colbyw5/boston_forecast/blob/master/visualizations/year_rolling_temp.png)

Language/packages: Coding is done in python via jupyter notebooks.  Packages used in this project include pandas, statsmodels, keras, matplotlib and sklearn.

Results: a plot of the test data with SARIMA and LSTM predictions is below.

![](https://github.com/colbyw5/boston_forecast/blob/master/visualizations/models_test.png)

Based on visual evaluaiton and RMSE, the SARMIA model provided a better fit to the data.

- SARIMA RMSE: 1.62
- LSTM RMSE: 4.97

Below is our forecast for 2020 monthly temperature in Boston using our SARIMA model

![Monthly Temperature in Boston 1989-2019, Forecast for 2020](https://github.com/colbyw5/boston_forecast/blob/master/visualizations/2020_Forecast.png)


