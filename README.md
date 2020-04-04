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
![alt text](https://github.com/faheemcodes/stocks/blob/master/Data/Stocks%20time%20series%20plot.JPG "Time Series Plot of Stocks")

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
> This notebook uses the python module called BeautifulSoup to scrap the yahoo finance website to obtain various parameters associated with each of the stock (eg: Revenue2019, EBITDA2018, Trailing P/E ratio etc).
> A python function which more or less generalises various pages of yahoo finance is created:
```python
def profiledata(ticker, page, attr, position):
# This function takes 
#       - ticker (eg: AAPL)
#       - page (eg: financials or balance-sheet or key-statistics)
#       - attr (eg: Net Income, Revenue etc from each of the pages. Works with most but not all attributes)
#       - position (eg: 1, 2, 3 etc. What is the column number where the data is located)

# Sample queries:
rev2019 = profiledata(t, 'financials', 'Total Revenue', 2 ) # t is the stock ticker
```

 - [**004 Sector Wise Analysis - 2008 Crash**](https://github.com/faheemcodes/stocks/blob/master/004%20Sector%20Wise%20Analysis%20-%202008%20Crash.ipynb):
 > This notebook analyses various sectors in the NASDAQ market to see the trends of fall and raising up during the financial crisis of 2008-2009
 > For each sector index, a reference value of stock is obtained (which is the value of the index in the beginning of september 2008 - right before the crash) - Reference value
 > During the recession, most of the stock indices fell to it bottom during the beginning of 2009 and went back up. The assessment calculates number of years it took for each sector to get back up to the reference value in 2008 Sept from the bottom most point in 2009 beginning. 
 ![alt text](https://github.com/faheemcodes/stocks/blob/master/Data/Sector%20indices%20-%202008%20Crash.JPG "Sector wise stock price crash")
  
 - [**005 Stock Prediction (Day Trading)**](https://github.com/faheemcodes/stocks/blob/master/005%20Stock%20Prediction%20(Day%20Trading).ipynb):

> This notebook uses artificial recurring neural networks architecture (LSTM) to predict the stock prices - Day ahead forecasting. 
> For a sample stock, the high prediction accuracy of this model on the test set is reflected in the following plot:
![alt text](https://github.com/faheemcodes/stocks/blob/master/Data/Stock%20prediction%20AAPL%20-%20Day%20ahead.JPG "Day ahead forecasting of Apple stocks - Prediction accuracy")
