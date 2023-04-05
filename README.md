
# Calculating and Comparing Rates of Return in Python:





## Table of Content


**1. NSE - Calculating and Comparing Rates of Return in Python**
  - INFOSYS (NSE) - Simple Returns
  - INFOSYS (NSE) - Logarithmic Returns
  - Calculating the Risk of a Security - INFY, HINDALCO
  - NIFTY - Logarithmic Returns

**2. USE Stocks - Calculating and Comparing Rates of Return in Python**
  - Microsoft - Simple Returns
  - Microsoft - Logarithmic Returns
  - Calculating a Portfolio of Securities' Rate of Return - PG, MSFT, F, GE

## Project Description

Calculating and Comparing Rates of Return in Python:
The rate of return of an investment is the percentage change in its value over a specific period of time. This project aims to calculate the rate of return of an investment in PYTHON using:
 - Simple Returns: The most common way of calculating the rate of return of a security. It assume that the investment grows at a constant rate over the period, ignoring any changes in the value of the investment during the period.

```bash
Formula:
Stock['simple_return'] = (Stock['close'] / Stock['close'].shift(1)) - 1
```

 - Logarithmic Returns: Assume that the investment grows at a variable rate over the period, taking into account any changes in the value of the investment during the period.

 ```bash
Formula:
Stock['simple_return'] = np.log(Stock['close'] / Stock['close'].shift(1))
```

 - Calculating a Portfolio of Securities' Rate of Return: To calculate the rate of return of a portfolio of securities, you need to take into account the weights of each security in the portfolio.

  ```bash
Formula:
pfolio = str(round(np.dot(annual_returns, weights),4)*100) + '%'
```

## Installation

To install iexfinance:

url: <https://pypi.org/project/iexfinance/>

url: <https://iexcloud.io/>
```bash
pip install iexfinance
```
To install NSEpy:

url: <https://nsepy.xyz/>
```bash
pip install nsepy
```

## Deployment

To deploy this project run

```bash
  import numpy as np
  import pandas as pd
  import matplotlib.pyplot as plt
  from datetime import datetime
  from pandas_datareader import data as wb
```

```bash
  from iexfinance.stocks import Stock, get_historical_data

  start = datetime(2018, 1, 1)
  end = datetime(2023, 3, 23)

  api_key = 'API_KEY'
```

Creating a portfolio:
```bash
tickers = ['PG', 'MSFT', 'F', 'GE']
mydata = pd.DataFrame()
for t in tickers:
    mydata[t] = get_historical_data(t, start, end, output_format = 'pandas', token=api_key)['close']
```

