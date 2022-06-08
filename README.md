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

%matplotlib inline
```

## Usage

## Conclusion

## Contributors
Sungmoo Ban, Ryan Johnson, Jung Kim, Jennifer Taylor, Danica Valera

