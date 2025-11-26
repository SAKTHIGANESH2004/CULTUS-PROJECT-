HAR-ARIMA Energy Load Forecasting
Project Overview:

This project implements an expert-level HAR-ARIMA model to forecast hourly electricity demand using a high-frequency PJM dataset. The dataset exhibits clear hourly, daily, and weekly seasonality. The aim is to build a transparent, interpretable, and accurate forecasting baseline that satisfies all analytical, modeling, and comparison requirements.

 Methodology:

The HAR-ARIMA structure explicitly models three time scales:

Lag-1 (θ₁): Intraday short-term behavior

24-hour mean (θ₂): Daily diurnal pattern

168-hour mean (θ₃): Weekly business cycle

ARIMA orders (p, d, q) and hierarchical lag parameters were selected using ACF/PACF analysis and AIC/BIC criteria. The model is fully documented with structured parameter blocks.

Baseline Comparisons:

Three models were trained and tuned:

HAR-ARIMA: Multi-scale memory modeling, strong accuracy, lightweight computation

SARIMA: Used as a statistical baseline for seasonal patterns

XGBoost: Feature-engineered ML baseline using lags & Fourier terms

Performance is compared using MAE, RMSE, and MAPE. HAR-ARIMA achieved a strong balance of speed, interpretability, and prediction quality, outperforming SARIMA and matching ML performance with fewer engineered features.

: Data & Tasks Completed

Two-year hourly PJM load data documented

Full HAR-ARIMA implementation with custom hierarchical lag structure

SARIMA and XGBoost baselines trained

Comparative analysis + final structured model configuration included
