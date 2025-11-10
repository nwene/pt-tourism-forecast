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

## Tech Stack

- R (e.g. `fpp3`, `forecast`, `tsibble`) or Python (e.g. `pandas`, `statsmodels`) – update based on what you used
- R Markdown / Jupyter Notebook for analysis and reporting

## How to Run

1. Clone the repo:
   ```bash
   git clone https://github.com/<your-username>/portugal-tourism-forecast.git
   cd portugal-tourism-forecast

2.  Open the R Markdown / notebook file: pt_tourism_forecast.Rmd 
3.  Install required packages (listed in requirements.txt or the R setup chunk).
4.  Knit/run the analysis to reproduce the figures and forecasts.

## Possible Extensions
  Compare SARIMA with ETS / Prophet models

  Add confidence intervals to forecasts for decision support

  Build an interactive dashboard (Shiny / Streamlit) to visualise forecasts
