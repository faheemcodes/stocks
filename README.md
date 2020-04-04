# Stocks - Data Scraping, Analysis and Forecasting
Various notebooks for accessing, scraping, downloading, forecasting of stock data.

- [**001 Plotting Time Series Data - Stocks**](https://github.com/faheemcodes/stocks/blob/master/001%20Plotting%20Time%20Series%20Data%20-%20Stocks.ipynb):
> This notebook plots takes in the tickers of various stocks and creates a time series plot (using Bokeh module in python) of all the stocks corresponding to the tickers provided in the input list and the specified start & end dates. 
  ```python
  tickers = ['AAPL','MSFT','GOOG'] # Tickers of the stocks that need to be plotted.
  start = '2000-01-01' # Start date
  end = '2020-03-30' # End date
```
> Sample plot will look something like this:
![alt text](https://github.com/faheemcodes/stocks/blob/master/Data/Stocks%20time%20series%20plot.JPG "Logo Title Text 1")

- [**002 Updating google sheets with Python - stock parameters**](https://github.com/faheemcodes/stocks/blob/master/002%20Updating%20google%20sheets%20with%20Python%20-%20stock%20parameters.ipynb):
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
- [**003 Scraping yahoo finance website using python**](https://github.com/faheemcodes/stocks/blob/master/003%20Scraping%20yahoo%20finance%20website%20using%20python.ipynb):

