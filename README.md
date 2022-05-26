# CNN_based_StockMarketPrediction
## Assignment 1
### Dataset used : Electric_Production.csv
Time series dataset of electricity production was taken for the forecasting models and it has two columns : one column being the date and the other column being the electricity produced, in the period between 1985 and 2018.
### Code :
The code for the assignment is present in the file SoC_Assignment1.ipynb.
### Instructions for running the code :
To run the code, upload the .ipynb file to Google Colab and run Colab using GPU accelerator. Then upload the dataset csv file to Colab and run the whole notebook sequentially.
### Explanation of the code :
Firstly, imported the packages like pandas, numpy and matplotlib and then imported data from csv dataset and printed first five entries to check that data is succesfully imported.Then visualised the data by plotting Production vs Date graph and also generated a scatter plot to observe various data points. <br />
Next, imported the statsmodels package and used the Python function called 'seasonal_decompose' to decompose the time series data into four components, namely : observed, trended, seasonal and residual. And after decomposition, it was observed that there is an overall increasing trend and yearly seasonality. Then the next important task was to check for the stationarity of data since we need to stationarize time series data for model fitting. For checking stationarity of data, firstly plotting the rolling statistics : mean and standard deviation, over the window of last 12 values. To confirm what was observed in this plot, Dickey Fuller test was performed on this raw data and got p-value greater than 5%(critical value) meaning our data was non-stationary with 95% confidence. <br />
To stationarize the data, differencing and de-trending operation was performed on it. Then, data was split into training and testing set : 80% training and 20% testing. <br /> 







