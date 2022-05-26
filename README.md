# CNN_based_StockMarketPrediction
## Assignment 1
### Dataset used : Electric_Production.csv
Time series dataset of electricity production was taken for the forecasting models and it has two columns : one column being the date and the other column being the electricity produced, in the period between 1985 and 2018.
### Code :
The code for the assignment is present in the file SoC_Assignment1.ipynb.
### Instructions for running the code :
To run the code, upload the .ipynb file to Google Colab and run Colab using GPU accelerator. Then upload the dataset csv file to Colab and run the whole notebook sequentially.
### Explanation of the code :
Firstly, imported the packages like pandas, numpy and matplotlib and then imported data from csv dataset and printed first five entries to check that data is succesfully imported. 
Then visualised the data by plotting Production vs Date graph and also generated a scatter plot to observe various data points. <br />
Next, imported the statsmodels package and used the Python function called 'seasonal_decompose' to decompose the time series data into four components, namely : observed, trended, seasonal and residual. And after decomposition, it was observed that there is an overall increasing trend and yearly seasonality. Then the next important task was to check for the stationarity of data since we need to stationarize time series data for model fitting. For checking stationarity of data, firstly plotting the rolling statistics : mean and standard deviation, over the window of last 12 values. To confirm what was observed in this plot, Dickey Fuller test was performed on this data and obtained p-value greater than 5%(critical value) meaning our data was non-stationary with 95% confidence. <br />
Then, to stationarize the data, de-trending and differencing was performed. Then the data was split into training and testing set : 80 % for training and 20% testing. <br />
Two forecasting models, namely SES(Simple Exponential Smoothing) and Holt's Linear trend method were evaluated and their performance was compared using the RMS error as the metric. <br />
SES model calculates forecasting data using weighted averages and the parameter 'alpha' affects the smoothing level. <br />
Holt's Linear trend model calculates forecasting data using level smoothing parameter 'alpha' and trend smoothing parameter 'beta'. If 'beta' is 0, then it works the same way as SES model. <br />






