# 📦 MARFIMA: Modified Autoregressive Fractional Integrated Moving Average Modeling in R

This package provides tools for fitting and simulating MARFIMA models — an extension of ARFIMA models with modified fractional differencing, allowing improved modeling of long-memory time series data. It includes flexible estimation of the fractional differencing parameter via GPH or Whittle methods, and functionality for diagnostics, simulation, and performance metrics.

## 🔧 Installation

Clone or download this repository, then source the R files manually or install as a local package:

```R
# Option 1: Source R scripts manually
source("Marfima_fit.R")
source("simulate_marfima.R")

# Option 2: Install as local package (requires devtools)
devtools::install("path/to/marfima")
```

# 📈 Core Functions
Marfima_fit(data, p, d, q, method, d_method, verbose)
Fits a Modified ARFIMA (MARFIMA) model to a univariate time series.

Arguments:

data: Numeric vector (time series)

p, q: Non-seasonal AR and MA orders

d: Differencing parameter (can be estimated if not provided)

P, D, Q: Seasonal AR, differencing, and MA orders (optional, default = 0)

method: ARIMA estimation method ("ML" or "CSS")

d_method: Estimation method for d if not provided ("GPH" or "Whittle")

verbose: Logical; whether to display ACF and PACF plots

Returns:
