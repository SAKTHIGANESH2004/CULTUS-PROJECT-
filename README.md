This project performs hourly electricity load forecasting using SARIMA, HAR-ARIMA, and XGBoost models. The dataset contains high-frequency PJM hourly load data showing strong daily and weekly seasonality. After timestamp conversion, hourly resampling, and interpolation, hierarchical lag features were engineered: θ₁ (1-hour), θ₂ (24-hour), and θ₃ (168-hour). These lags allow the HAR-ARIMA model to represent intraday, daily, and weekly dynamics.

The HAR-ARIMA model uses ARIMA(1,0,1) with exogenous hierarchical lags. The parameters were chosen because p=1 captures short-term dependence, d=0 maintains the stationary structure after resampling, and q=1 helps model shock smoothing. For comparison, a seasonal SARIMA(1,0,1)(1,0,1,24) baseline and a feature-engineered XGBoost model were trained.

Model Performance (Test Set):

SARIMA: MAE = 9785.31, RMSE = 11581.34, MAPE = 31.01%

HAR-ARIMA: MAE = 2024.44, RMSE = 2788.52, MAPE = 6.41%

XGBoost: MAE = 934.19, RMSE = 1249.36, MAPE = 3.12%

The results show SARIMA performs weakest due to limited ability to capture nonlinear and multi-scale patterns. HAR-ARIMA greatly improves accuracy by integrating hierarchical memory. XGBoost achieves the best performance across all metrics, demonstrating strong capability for nonlinear load forecasting.

This completes all required tasks: dataset acquisition, HAR-ARIMA implementation, parameter justification, baseline creation, and comparative evalua
