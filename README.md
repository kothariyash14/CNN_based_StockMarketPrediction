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
## Assignment 2
### Dataset used :
A subset of MosMedData: Chest CT Scans with COVID-19 Related Findings Dataset, containing lung CT scans with COVID-19 related findings, as well as without such findings.
### Code :
The code for the assignment is present in the file SoC_Assignment2.ipynb.
### Instructions for running the code :
To run the code, upload the .ipynb file to Google Colab and run Colab using GPU accelerator. Run the whole notebook sequentially.
### Explanation of the code :
Firstly, imported the packages like tensorflow, numpy and matplotlib and then downloaded data from the CT scans dataset. <br />
Then, data was loaded and nibabel package was imported to read the scans, which were in nifti format.To process the data, firstly 3D volume was rotated by 90 degrees to fix the orientation.Then raw intensity(in HU units) was scaled to be between 0 and 1. Width, height and depth were resized. <br />
Then the the scans were read from the class directories and labels were assigned. Scans were downsampled to have dimensions 128x128x64. Raw HU values were rescaled in the range 0 to 1. Lastly, splitted the dataset into train and validation subsets. Then data augmentation was performed by rotating the volume at random angles while training. For performing 3D convolutions on the data, a dimension of size 1 was added at axis 4, making new shape as (samples, height, width, depth, 1). <br />
Then, the 3D CNN was defined setting width, height and depth to be of 128, 128 and 64 unit respectively. To train the model, learning rate was kept very small(0.0001) and 100 epochs were decided for training. The loss function was binary cross-entropy. The prediction was then made on a single CT scan and confidence % was calculated.



