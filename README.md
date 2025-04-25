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

### 📤 Returns

- **`model`**: Fitted ARIMA model on fractionally differenced data.  
- **`results`**: Data frame of model evaluation metrics:
  - AIC, BIC, AICc, BICC  
  - RMSE: Root Mean Squared Error  
  - MAPE: Mean Absolute Percentage Error  
  - MPE: Mean Prediction Error  
  - NMSE: Normalized Mean Squared Error  
  - Estimated `d` (if applicable)

---

## 🔁 Function: `simulate_marfima()`

Simulates a time series from a MARFIMA model (no seasonality).

### 📥 Arguments

- **`n`**: Number of time points to simulate.  
- **`phi`**: AR coefficients (numeric vector).  
- **`theta`**: MA coefficients (numeric vector).  
- **`dfrac`**: Fractional differencing value (e.g., 0.3).  
- **`dint`**: Integer differencing order (e.g., 1 or 2).  
- **`burnin`**: Number of initial observations to discard *(default = 100)*.  
- **`seed`**: Optional seed for reproducibility.

### 📤 Returns

- A simulated time series (`ts` object).

---

## 🔍 Example Usage

```r
# Simulate a MARFIMA(1, 2 + 0.3, 1) process
set.seed(6533)
sim_data <- simulate_marfima(n = 5000, phi = 0.2, theta = 0.3, dfrac = 0.3, dint = 2)

# Fit a MARFIMA model with automatic d estimation using Whittle method
fit <- Marfima_fit(sim_data, p = 1, q = 1, d_method = "Whittle")

# View model performance
print(fit$results)
```

---

## 📚 Dependencies

Before using MARFIMA, install the following R packages:

```r
install.packages(c("forecast", "fracdiff", "MASS"))
```

## 👤 Author

**Abubakar Bello**  
🧑‍💻  Statistics |Data Scientist | Time Series Analyst  
📧 Email: [bellobajogagsu@gmail.com](mailto:bellobajogagsu@gmail.com)  
🔗 GitHub: [github.com/belloabubakarbajoga](https://github.com/belloabubakarbajoga)  
📍 Gombe State, Nigeria  

