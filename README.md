# Stocks - Data Scraping, Analysis and Forecasting
Various notebooks for accessing, scraping, downloading, forecasting of stock data.

- **001 Plotting Time Series Data - Stocks**:
> This notebook plots takes in the tickers of various stocks and creates a time series plot (using Bokeh module in python) of all the stocks corresponding to the tickers provided in the input list and the specified start & end dates. 
  ```python
  tickers = ['AAPL','MSFT','GOOG'] # Tickers of the stocks that need to be plotted.
  start = '2000-01-01' # Start date
  end = '2020-03-30' # End date
```
- **002 Updating google sheets with Python - stock parameters**:
> This notebook requires you to obtain a google sheets api credentials and store it locally to access the google sheets. Learn more about setting this from this video from [Tech with Tim](https://www.youtube.com/watch?v=cnPlKLEGR7E). 
> After the previous step, the code to access the data from yahoo finance and then updating the sheet is quite easy and a sample goes like this:
```python
# Importing yahoo finance api and calling the yahoo finance object using the ticker string, t
import yfinance as yf
s = yf.Ticker(t) 
# Obtain the sector of the stock
sector = s.info.get('sector') 
# Update the 11th column in the google sheet with the sector name
sheet1.update_cell(i+2,11,sector) 
```

