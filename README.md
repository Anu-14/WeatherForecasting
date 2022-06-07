# WeatherForecasting
## Analysis of weather
The variation of temperature is analyzed through the years with many plots, including
line charts with and without markers, scatter plots, box plots.
Scikit-learn is used to implement unsupervised learning and plot the number of clusters
versus the sum of squared distances to get groups of similar temperatures. Plotting
cluster maps for different values of KMeans to see the variation of temperature in
various seasons of the year.
Histogram plots are used to see the occurrences of temperature values in the years
throughout the timeline of data. The colored histogram is used to get the month of a
particular frequency.
A line chart and scatterplot are used to observe the variation of average temperature in
India throughout the time period. A LOWESS(Locally weighted Scatterplot Smoothing)
trendline is drawn with the scatter plot, which is non-linear. This also shows that the
average temperature is increasing faster than we think.
When we plot the variation of temperature over the years in every month separately, we
see that there are more fluctuations and a higher temperature change in some months
like February and March.
In the pair-plot, we can see the relationship between the different entities and their
correlation.
The plot for different seasons shows that the average temperature rises significantly in
all seasons. The animation plot highlights the variation in temperature over the years in
different months

The forecasting is done using two methods:
1. Decision tree regression
2. SARIMA model
## Decision Tree Regression:
The non-linearity in the data is accommodated with the use of decision tree regression
for prediction. The data is divided into two sets for training and testing. Here, the
training size is taken as 0.7, and the remaining is for testing. We predict values for the
testing dataset after fitting the training x and y values and get the r2 score close to one
depicting good accuracy of the model. Then temperature for 2018 (next year for the
dataset) is calculated and plotted.
## SARIMA (Seasonal AutoRegressive Integrated Moving Average):
Considering the seasonal trend in a year, the SARIMA model is used for forecasting. The
autocorrealtion and partial autocorrelation plots show that the data is non-stationary.
Also, the ADF statistic is not less than the critical values, and the p-value is not less than
0.5 showing that the data is not stationary. So, the zero and first differentiated ARIMA
models are used. The data is again divided into train and test data. A function
optimize_ARIMA is used to get the p and q values and the corresponding AIC (Akaike's
Information Criterion) for the zero and the first differentiated model. The combinations
of p and q that range from {0,1,2,...,10} take time to get the AIC values. Then two
combinations with minimum AIC values are selected. Plot diagnostics are drawn for both
models, and it's observed that they are very similar. Then, the forecast is done for the test
split using both combination models. The zero-differentiated model's forecast is plotted
with the actual data and confidence intervals for better comparison.
