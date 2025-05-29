
# Smart Energy Demand Forecasting using Time Series Modeling and Anomaly Detection

📌 Project Overview

This project focuses on forecasting electricity demand and solar energy generation using real-world time series data. The goal is to enable energy providers to optimize power production, reduce operational costs, and maintain grid stability.

To achieve this, the project employs:

ARIMA & SARIMAX for linear and seasonal forecasting

XGBoost Regressor for accurate, non-linear demand prediction

Isolation Forest for detecting anomalies in solar generation data
# 🎯 Objectives

Accurately predict electricity demand to help a company optimize power generation

Forecast energy demand using historical time-stamped data

Predict solar energy generation for the next 30 days

Detect anomalies during daylight solar generation for risk mitigation

Improve operational planning and reduce dependency on emergency power backups
# 🛠️ Tech Stack & Tools
Python (Pandas, NumPy, Matplotlib, Seaborn)

Statsmodels for ARIMA & SARIMAX

XGBoost for advanced regression modeling

Scikit-learn for anomaly detection using Isolation Forest

IsolationForest for anomaly detection
# 🗂️ Dataset Description
The dataset contains hourly time series data spanning from 2016. It includes:

datetime — Timestamp of each observation (hourly granularity)

IT_solar_generation — Hourly solar energy generated (in watts)

IT_load_new — Hourly energy load consumption by IT infrastructure



# Engineered Features


## Lag features: 

lag1, lag2, lag3, lag4, lag5 — previous values for temporal dependency

## Rolling statistics:

rolling_mean_3, rolling_std_3 — moving average and standard deviation over 3 values

rolling_min_5, rolling_max_5 — min and max over 5-value window

## Time-based features:

hours, dayofweek, month, year
# 🔍 Forecasting Models
## ARIMA

Suitable for linear trends, performed poorly with seasonal and non-linear data

RMSE: 7808 (IT Load), 2486 (Solar)

## SARIMAX

Handles seasonality better, improved over ARIMA

RMSE: 5667 (IT Load), 1337 (Solar)

## XGBoost Regressor

Best performance for both IT Load and Solar Generation

Captured non-linearity, seasonality, and noise well

RMSE: 890 (Solar), ~880–1100 (IT Load)
# ⚡ Decision-Making Insights

## Solar Generation Forecast

Generation remains near-zero until sunrise (4–6 AM)

Peaks between 8 AM to 4 PM, then drops post sunset

Forecasted peak slightly lower than historical (due to possible cloudy days or reduced sunlight)

Recommendation: Use solar backups or IT power as failsafe on cloudy/rainy days

## IT Power Load Forecast

Shows stable and consistent M-type pattern (daily up-down)

No risk of sudden drops or spikes

Recommendation: No need for emergency batteries or additional power support currently
# 🚨 Anomaly Detection

Applied Isolation Forest on daylight solar generation hours

Helps identify unexpected behavior (e.g., cloudy days, panel faults)

Found 48 key anomalies (5%) in daytime generation
# 💡 Future Improvements

Integrate real-time weather data (cloud, temp, humidity)

Add multivariate forecasting with hybrid models

Build an interactive dashboard (Tableau/Streamlit)

Explore deep learning models like LSTM/Transformer
# 👨‍💻 Author
Prabhjot Singh  Information Technology | Marymount University AI Enthusiast | Building end-to-end ML/DS projects


# ⭐ GitHub Tags

#TimeSeries #Forecasting #XGBoost #SolarEnergy #AnomalyDetection #EnergyAnalytics