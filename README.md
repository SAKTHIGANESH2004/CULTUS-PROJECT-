 Advanced Time Series Forecasting with Hierarchical ARIMA

This project focuses on forecasting electricity demand using models that capture the natural multi-scale patterns found in real energy data. Using the PJM hourly load dataset—which shows clear hourly, daily, and weekly cycles—the work builds a Hierarchical ARIMA (HAR-ARIMA) model that uses three key lags: 1 hour, 24 hours, and 168 hours. These lags represent short-term behavior, day-to-day repetition, and weekly routines, giving the model a structured understanding of how demand evolves over time.

To judge its performance, HAR-ARIMA is compared with two common baselines: a 24-hour Seasonal ARIMA model and an XGBoost regressor trained on the same engineered lags. All models are trained on 80% of the data, and evaluated on the remaining 20% using MAE, RMSE, and MAPE. Visual checks—prediction curves, residual plots, and error distributions—help reveal where each model performs well or struggles.

The findings show that HAR-ARIMA handles both short- and long-range patterns more effectively than SARIMA, while XGBoost provides strong nonlinear performance but tends to smooth peak demand. Overall, the project demonstrates a clear, practical workflow for improving load forecasting using hierarchical time-series structure.
