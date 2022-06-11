# Options Trading
## Hypothesis
Leveraging the fb prophet machine learning tool, input stock price data and create short-term predictions for a particular stock. Using yfinance options pricing data we will compare against the predicted prices, calculating profit probability for various confidence levels of the predicted stock price. The end goal is to determine and rank order the most profitable options trades for a specified window of time. We will then backtest these "maximized profitable trades'' against actual trading results.
## Technologies:
* FB Prophet
* YFinance

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

## Conclusion
Our main goal was to create a machine learning function to predict the most profitable strike price during a specific time period. For the sake of our presentation, we used Microsoft as an example. In the end, we analyzed that the most profitable strike price for Microsoft on June 17th was $265 with a 210% percentage gain. 

![unnamed](https://user-images.githubusercontent.com/97059769/173182187-5d035839-c6d0-413d-a2a2-e3cdd45e7987.png)


One main issue we ran into was how far back we pulled our data. We originally pulled data for 5 years, however, this caused our predictions to be fairly inaccurate due to the volatility of the stock over the years. To prove this theory, we decided to retrieve the accuracy scores of each duration by calculating the mean absolute percentage score. With the MAPE, the closer the percentage is to 0%, the more accurate the model is. Although the percentage scores are fairly similar amongst the time periods, the most accurate model was our 1 year model at 2.28%. So in the end, instead of pulling data from 5 years out, we pulled it for 1 year instead.

<img width="698" alt="Screen Shot 2022-06-10 at 11 26 28 PM" src="https://user-images.githubusercontent.com/97059769/173182134-92d652df-28e8-4e11-b085-636eded56a33.png">


## Next Steps

## Contributors
Sungmoo Ban, Ryan Johnson, Jung Kim, Jennifer Taylor, Danica Valera

