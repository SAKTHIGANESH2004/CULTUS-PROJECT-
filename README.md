# CULTUS-PROJECT-📘 Project Summary – Advanced Time Series Forecasting with Hierarchical ARIMA

This project examines electricity demand forecasting through a modeling framework that blends classical time-series methods with hierarchical lag structures. Using the PJM hourly load dataset—well known for its clear intraday rhythm, daily regularity, and weekly consumption cycles—the work explores how multi-scale temporal patterns can be used to improve predictive accuracy.

The central model in the study is a Hierarchical ARIMA (HAR-ARIMA) specification. Instead of relying solely on short-term autoregressive terms, the model incorporates three lagged features chosen to mirror distinct temporal horizons: a 1-hour lag to represent immediate persistence, a 24-hour lag to capture day-over-day patterns, and a 168-hour lag to reflect the weekly consumption cycle. This hierarchy is particularly suitable for electricity load data, where consumer behavior repeats across multiple nested time scales.

To evaluate the effectiveness of this structure, the project compares HAR-ARIMA with two established baselines. The first is a seasonal ARIMA model configured with a 24-hour cycle, which is traditionally used for load forecasting. The second baseline is XGBoost, trained on the same engineered lag features. This comparison highlights the contrast between linear, seasonally driven statistical models and a nonlinear, tree-based learner.

All models are trained on the first 80% of the dataset, with performance assessed on the remaining 20%. Metrics include mean absolute error, root mean squared error, and mean absolute percentage error. Along with numerical evaluation, the project includes visual inspection through prediction curves, residual time-series plots, and distribution analyses. These diagnostics help reveal model biases, the stability of forecast errors, and the extent to which each method captures peak-load behavior.

The results illustrate the usefulness of hierarchical lag structures: HAR-ARIMA captures both short-range dynamics and broader seasonal tendencies without overfitting. SARIMA performs reasonably well on daily patterns but shows limitations at the weekly scale. XGBoost, while flexible, depends strongly on feature preparation and tends to smooth extreme values.

Overall, the project offers a clear demonstration of how structured, multi-horizon information can enhance load forecasting and provides a reproducible workflow suitable for practical energy-analytics applications.
