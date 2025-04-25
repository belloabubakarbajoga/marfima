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

# 📥 Arguments 
  - `data`: Numeric vector representing the time series. 
  - `p`, `q`: Non-seasonal autoregressive (AR) and moving average (MA) orders. 
  - `d`: Differencing parameter. Can be manually specified or estimated if not provided. 
  - `method`: ARIMA estimation method. Options: - `"ML"`: Maximum Likelihood - `"CSS"`: Conditional Sum of Squares
  - `d_method`: Method for estimating the fractional differencing parameter `d`:
  -  `"GPH"`: Geweke–Porter–Hudak estimator - `"Whittle"`: Whittle likelihood-based estimator
  -  `verbose`: Logical; if `TRUE`, shows ACF and PACF plots for diagnostic purposes.
# 📤 Returns:
 - 
      -  `model`: The fitted ARIMA model object (on fractionally differenced series).
      - `results`: A data frame with model performance metrics:
          - **AIC**: Akaike Information Criterion
          -  **SBIC**: Bayesian Information Criterion
          -  **RMSE**: Root Mean Squared Error
          -  **MAPE**: Mean Absolute Percentage Error
          - **MPE**: Mean Prediction Error 
          - **NMSE**: Normalized Mean Squared Error 
          - **Estimated `d`** (if estimated) 
