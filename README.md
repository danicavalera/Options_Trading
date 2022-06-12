# Options Trading
## Hypothesis
Leveraging the fb prophet machine learning tool, input stock price data and create short-term predictions for a particular stock. Using yfinance options pricing data we will compare against the predicted prices, calculating profit probability for various confidence levels of the predicted stock price. The end goal is to determine whether or not a specific option is profitable for a specified window of time and to provide the best strike price to buy in.

## Technologies:
* [FB Prophet](https://facebook.github.io/prophet/) - procedure for forecasting time series data based on an additive model
* [YFinance](https://pypi.org/project/yfinance/) - open-source tool that uses Yahoo's publicly available API for stock/options data
* [scipy](https://scipy.org/) - Fundamental algorithms for scientific computing in Python
* [matplotlib](https://matplotlib.org/) - comprehensive library for creating static, animated, and interactive visualizations in Python
* [numpy](https://numpy.org/) - fundamental package for scientific computing with Python
* [hvplot](https://hvplot.holoviz.org/) - high-level plotting API for the PyData ecosystem built on HoloViews
* [holoview](https://holoviews.org/) - open-source Python library designed to make data analysis and visualizatio

## Installation Guide
Before running the application first install the following dependencies:

```python
import pandas as pd
import yfinance as yf
from scipy.stats import norm
import matplotlib.pyplot as plt

from prophet import Prophet

import numpy as np
import hvplot.pandas
import holoviews as hv
from holoviews import opts
hv.extension('bokeh')

```

## Usage
To run this machine learning tool, simply input the ticker you want to use and how far back you want to pull the data:

![Screen Shot 2022-06-11 at 7 16 58 AM](https://user-images.githubusercontent.com/97059769/173198050-a7f79b24-8f95-49cb-8285-f07aba49f4fd.png)


## Conclusion
Our main goal was to create a machine learning function to predict the most profitable strike price during a specific time period. For the sake of our presentation, we used Microsoft as an example. In the end, we analyzed that the most profitable strike price for Microsoft on June 17th was $262.50 with a 127% percentage gain. 

![unnamed](https://user-images.githubusercontent.com/97059769/173182187-5d035839-c6d0-413d-a2a2-e3cdd45e7987.png)


One main issue we ran into was how far back we pulled our data. We originally pulled data for 5 years, however, this caused our predictions to be fairly inaccurate due to the volatility of the stock over the years. To prove this theory, we decided to retrieve the accuracy scores of each duration by calculating the mean absolute percentage score. With the MAPE, the closer the percentage is to 0%, the more accurate the model is. Although the percentage scores are fairly similar amongst the time periods, the most accurate model was our 1 year model at 2.28%. So in the end, instead of pulling data from 5 years out, we pulled it for 1 year instead.

<img width="698" alt="Screen Shot 2022-06-10 at 11 26 28 PM" src="https://user-images.githubusercontent.com/97059769/173182134-92d652df-28e8-4e11-b085-636eded56a33.png">

## Accuracy Model
Using historical stock data, we used MAPE model to get the best matching forecast scores by comparing real stock data for a week and fbprophet result with the same period of time. We tested with volume of 6 month, 1 year, and 3 year data. 
The most accurate result that we got for the time period from this model is "1 Year". So we applied 1 year period in order to get the most accurate value.


## Next Steps
* Apply to daily price of options swings
* Apply more math algorithm to get different dimensions of output
* Other machine learning models including Neural Network
* Backtest with historical option price
* Define functions to automate the process of pulling data 
* Develop Robo adviser using AWS  Lex, Sagemaker, S3 
* Add risk tolerance inputs to adjust our predictions

## Contributors
Sungmoo Ban, Ryan Johnson, Jung Kim, Jennifer Taylor, Danica Valera

