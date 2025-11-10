# Portugal Tourism Forecasting (Time Series Project)

This project builds and evaluates forecasting models for monthly tourism in Portugal using official data from Eurostat. The goal is to model the strong seasonality in tourist arrivals and generate short-term forecasts that can support planning and policy decisions.

## Data

- **Source:** Eurostat – monthly tourism statistics for Portugal  
- **Frequency:** Monthly  
- **Variables:** Date (month), Number of tourists/overnight stays

## Methods

- Time series exploration (trend, seasonality, autocorrelation)
- Stationarity checks (unit root tests)
- Seasonal differencing and transformations
- SARIMA modelling (e.g. ARIMA(1,1,0)(1,1,2)[12])
- Residual diagnostics (ACF/PACF, Ljung–Box)
- Forecast accuracy evaluation (RMSE, MAE, MAPE)

## Results

- Final selected model: **Seasonal ARIMA** capturing yearly seasonality.
- Achieved low forecast error on the test set (e.g. MAPE around X% – update with your value).
- Forecasts successfully track seasonal peaks (tourist high season) and off-season lows.

## Model Comparison and Accuracy

I compared three SARIMA specifications on the test set:

| Model            | RMSE   | MAE    | MAPE  | MASE | RMSSE | ACF1   |
|------------------|--------|--------|-------|------|-------|--------|
| sarima110_011    | 55.53  | 47.51  | 3.31% | 0.60 | 0.52  | 0.36   |
| **sarima110_112**| **50.05** | **41.22** | **3.06%** | **0.52** | **0.46** | **0.31** |
| sarima111_112    | 52.29 | 42.65 | 3.11% | 0.54 | 0.49 | 0.33 |

The final chosen model is **sarima110_112**, a Seasonal ARIMA **ARIMA(1,1,0)(1,1,2)[12]**:

- **RMSE ≈ 50**, **MAE ≈ 41**, **MAPE ≈ 3.1%**
- Errors are small relative to the series scale (MASE < 1, RMSSE < 0.5)
- Residual autocorrelation at lag 1 is low (ACF1 ≈ 0.31), indicating a reasonable fit

This model captures the strong annual seasonality in Portuguese tourism while keeping forecast errors low.


## Tech Stack

- R (e.g. `fpp3`, `forecast`, `tsibble`) or Python (e.g. `pandas`, `statsmodels`) – update based on what you used
- R Markdown / Jupyter Notebook for analysis and reporting

## How to Run

1. Clone the repo:
   ```bash
   git clone https://github.com/nwene/pt-tourism-forecast.git
   cd portugal-tourism-forecast

2.  Open the R Markdown / notebook file: pt_tourism_forecast.Rmd 
3.  Install required packages (listed in requirements.txt or the R setup chunk).
4.  Knit/run the analysis to reproduce the figures and forecasts.

## Possible Extensions
- Compare SARIMA with ETS / Prophet models
- Add confidence intervals to forecasts for decision support
- Build an interactive dashboard (Shiny / Streamlit) to visualise forecasts
