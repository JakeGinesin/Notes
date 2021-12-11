###### tags: `COMP30760 - Data Science with Python`

# Time Series Analysis

## Static vs Dynamic Data
- We have largely focused on static datasets, which are collected at a fixed point in time and then no longer updated
- In many situations we do not have a single static dataset. The data is dynamic, arriving periodicaly or in a countinous stream
- In some dynmaic scenarios, we need to apply anlysis method s that can be effiicnetly updated to include new data
- Sometimes we will only want to take into account recent history, rather than all older historical data which may longer be relevant
- **Example**: "Want to develop a retail sales model that remains accurate as the business gets larger... However, the underlying source is changing; the business is growing, and so your guess of the sales given the previous few days of sles is probably going to be different form lastr year. So last year's data, when the business was small, is ont as relevant to this year, when the business is large"

## Time Series Data
- **Time Series**: A dataset consisting of the values of a function samples accross different points in time. Most commonly, a time series is a sequence taken at equally spaced points in time
- Time series data arise in many applications, from financial trading to natural occuring phenomena
- Often visualized by line charts
>
- We will often plot a time series, and then look for trends, periodic behaviour, seasonal variations, setep changes, outliers

## Comparing Time Series Data
- In real-world applications we will often be tracking multiple varia les over time, each represented by a different time series

## Characterising Time Series Data
- Key questions when looking at time series data:
    - Is the source sampled at equaly-spaced intervals?
    - How long and/or rapidly growing is the available series?
    - What is the best resolution/frequency to inspect the data?
    - Are there any noisy or outlying values in the series?
    - Are there any missing values in the data?

## Stationary Time Series
- A time series is stationary if its properties do not depend on the time at which the series is observed
- Summary statistics calculated on a stationary time series will be broadly consistent over time (e.g. mean, variance, etc)
- Many real-world time series datasets are non-stationary, as their statistical properies change over time

## Time Series Components
- There are many reasons for a time series to be non-stationary. Most time series analysis is based on the modelling assumption that the observed series is the sum of three componenets:
    - **Trend**: Shows the general tendency of the series to increase or decrease over a long period of time
    - **Seasonality**: Peaks and troughs that occur in a regular intervals including daily, weekly, monthly, or yearly cycles
    - **Noise**: The random fluctuations in the data which are left when the components are stripped

## Time Series Data Formats
- Most basic format for time series data involves observations with a date/time field and a single numeric target. The format of the date will depend on the data source and application domain.
- Data preprocessing steps will often be required to extract dates in a suitable format, or change the frequency of the data

## Python Data and Time types
- The build-in Python`datetime module
- From a datetime value, we can access its individual parts - i.e. the date and time components

```python=
d = datetime.now()
d.year
d.month
d.day
d.hour
```

- a `timedelta` is a python data type whihc stores the temporal difference between two datetime values
- We can add or subtract a `timedelta` value to an existing `datetime` value to get a new shifted date:

## Converting Between Strings and Dates

- Python `datetime` values can be formatted as strings with `strfttime()` and special formatting codes
- Each code is a placeholder for a date or time component of a datetime value

## Time Series in Pandas
- Most basic kind of time series daa in Pandas is a series indexed by timestamps, often `datetime` values
```python=
dates = [datetime(2016, 4, 2), datetime(2016, 4, 4), dateimte(2016, 4, 6)]
sales = [5, 10, 7]
ts = pd.Series(dates, sales)
```
- A pandas time series can be indexed and sliced in the same way as a normal series
- For longer time series, we can easily select slices of data for a specific month or year
- In real-world applications, we will usually be tracking multiple variables over time, each represnted by a different series
- Load a time series dataset from a CSV file as a Pandas Data Frame. Specify `parse-dates` to parse the index field as a date

```python=
df = pd.read_csv("random,csv", imdex_col="date", parse_dates=True)
df.head() # plot function
```

- Pandas has functionality for aggregating data and time based data. For example, we can group the data by year:

df_year = df.groupby(df.index.year).sum()
df_year.head()

## Sampling Frequency

- A key characteristic of a time series is how frequently observations are spaced in time. Normally observations will be evenly spaced. 
- Sampling frequency referes to how often the observations of a time series occur. For analysis, we may wish to alter the frequency.
- Resampling: Process of converting time seires data from one frequency to another. This is done in Pandas via the `resample()` function.
- We can downsample - i.e. aggregate data to a lower frequency

## Smoothing Time Series Data
- a *moving average* (also called rolling mean) is often applied to time series to smooth short-term variations and highlight the underlying trend in the series
- Example: US beef production

## Moving Average
- A simple moving average divides a series into overlapping regions of a fixed size, called "windows" (e.g. 7 days, 14 days, 1 month).
- Each value is calculated as the average of all the observations in the current window. We then "roll" the window forward by one observation and calculte the next value.

### Moving Averages in Python
- In Pandas we can compute a moving average for a Series or Data Frame by calling its `rolling()` function and specifying a window size (i.e. number of observations)
- We apply the function `mean()` to the result


## Missing Data in Time Series
- in many times series, values might be missing for certain time periods
- if there are missing values, there are two ways to deal with the incomplete data:
1. Drop the entire record
2. Inpute or estimate the missing information
### Replacing Data
- There are time series-specific methods ot estimate missing values
    - Last obseration carried forward (LOCF): Use the most recent previous non-missing value to estimate the urrent missing value
    - Next Observation carried backward (NOCB): Use the next non-missing value to estimate the current missing value
    - Linear interpolation: Fill in the missing data by assuming that the relationship between the variables follows a line
- Note: thse threee methods may not work well if there is a strong seasonal component in the time 

## Time Series Forecasting
- Time series forecasting uses a model to predict future values based on previously observed values in a time series
- Input: Past data provided to a model to make a forecast
- Output: Prediction for a future time point beyon the input data 
- Accuracy of the prediction will depend on the availability of past data. the trend in the data, and the forecasting horizon

### Application:
- Predict future daily sales based on historic sales data
- We could apply a variety of different approaches to make these spredictions (e.g. ARIMA, Prophet, dep learning LSTM methods)

## Outliers in Time Series Data
- An outlier in a time series is an observation that significantly differs from the other observations
- Detecting outliers is often important
- Can affect the performance of time series forecasting techniques
- Might represent errors in the data, or might occur for specific underlying reasons which need to be investigated

### Examples:
- Web Analytics: Spot unexpeted growth or drop in website hits
- Financial data: Detection of price manipulation or fraudulent behaviour i banking and stock market exchange
- Aviation: Aircraft sensor monitoring to observe potential disturbances
>
- Outliers might be visisble as unexpected spikes or troughs in a time series plot. Many more complex detection methods exist.
- A common approach: observations above n standard deviations from the mean are considered outliers 
