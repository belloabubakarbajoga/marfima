![image](https://github.com/user-attachments/assets/c015509e-d9fd-497a-841b-7a8e3833aad9)# 📦 MARFIMA: Modified Autoregressive Fractional Integrated Moving Average Modeling in R

This package provides tools for fitting and simulating MARFIMA models — an extension of ARFIMA models with modified fractional differencing, allowing improved modeling of long-memory time series data. It includes flexible estimation of the fractional differencing parameter via GPH or Whittle methods, and functionality for diagnostics, simulation, and performance metrics.

## 🔧 Installation

Clone or download this repository, then source the R files manually or install as a local package:

```R
# Option 1: Manually source the R scripts (if using raw files)
source("https://github.com/belloabubakarbajoga/marfima")
source("https://raw.githubusercontent.com/belloabubakarbajoga/marfima")
# Add additional script files as needed

# Option 2: Install the package locally using devtools (clone the repo first)
# Make sure you have devtools installed: install.packages("devtools")
devtools::install("path/to/cloned/marfima")

# Option 3: Install directly from GitHub
devtools::install_github("belloabubakarbajoga/marfima")


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

## 🤝 Contributors

Thanks to the following individuals for their contributions to the MARFIMA project:

| Name             | Role                     | GitHub  / Contact Email                                    |
|------------------|--------------------------|---------------------------------------------|
| Abubakar Bello   | Author / Maintainer      | [@belloabubakarbajoga](https://github.com/belloabubakarbajoga) |
| Musa Tasiu       | Contributor / Reviewer   | dagastatistician@gmail.com |
| H.G. Dikko       | Contributor / Reviewer   | hgdikko@yahoo.com          |
| B.B. Alhaji      | Contributor / Reviewer   | bbukar@nda.edu.ng          |



