# README — Brent Crude Oil Price Forecasting using Time Series Analysis

## Project Overview

This project aims to forecast Brent crude oil prices for the next 12 months using statistical time series forecasting techniques in Python.

## Dataset Information

### Dataset Details

**Dataset Title:** Brent Oil Prices

**Source:** Kaggle

**URL:** https://www.kaggle.com/datasets/mabusalah/brent-oil-prices

### Original Dataset Structure

Original dataset dimensions:

- 9011 observations
- 2 variables

Variables:

- Date
- Price

Dataset characteristics:

- Historical Brent crude oil prices
- Daily observations
- Long historical coverage period
- Suitable for time series forecasting applications

---

## Methodology Overview

The project follows a structured forecasting pipeline:

1. Data Acquisition
2. Data Cleaning and Preparation
3. Exploratory Data Analysis (EDA)
4. Log Transformation
5. Stationarity Testing
6. Differencing
7. ARIMA / SARIMA Model Development
8. Forecast Generation

Current Progress:

Completed:

- Data Acquisition
- Data Cleaning
- Exploratory Data Analysis
- Stationarity Analysis
- ARIMA Model Selection
- Forecast Generation
- Model Diagnostics

---

# Phase 1 — Data Acquisition and Preparation

## Data Preparation Methods

Several preprocessing steps were performed to prepare the dataset for forecasting.

### Date Processing

Date values were converted into time-series compatible format.

Purpose:

- Enable temporal analysis
- Support forecasting methodology

### Chronological Ordering

Historical observations were ordered chronologically.

Purpose:

- Maintain time-series integrity

### Time Index Construction

The date field was assigned as the time index.

Purpose:

- Enable resampling
- Support forecasting workflows

### Missing Data Assessment

The dataset was evaluated for:

- Missing values
- Temporal gaps
- Irregular spacing

Observation:

Historical oil market data naturally contains irregular spacing due to weekends and market closures.

---

## Monthly Aggregation

The forecasting objective targets monthly oil price prediction.

Daily observations were aggregated into monthly averages.

Monthly dataset dimensions:

- 427 observations
- 1 variable

Purpose:

- Reduce daily market noise
- Improve forecasting stability
- Align analysis directly with business objectives

---

# Exploratory Data Analysis (EDA)

Several visual analyses were performed to understand oil price behavior.

## Historical Trend Analysis

Observations:

- Brent crude oil prices demonstrate a long-term increasing trend
- Market fluctuations occur throughout historical periods
- Significant price disruptions appear during major economic events

Interpretation:

Oil market behavior reflects:

- Global economic activity
- Supply-demand changes
- Geopolitical influences

Energy Economics Perspective:

For hydrocarbon-dependent economies such as Qatar, oil price fluctuations directly influence national revenue planning and economic decision-making.

---

## Distribution Analysis

Observations:

- Oil prices exhibit right-skewed behavior
- Lower price levels occur more frequently
- High-price periods occur less frequently

Interpretation:

Oil price distributions are not normally distributed.

Implication:

Variance stabilization techniques are necessary before statistical forecasting.

---

## Structural Break Analysis

Major economic disruptions were identified through structural-break visualization.

Events examined:

- 1990 Gulf War
- 2008 Financial Crisis
- 2014 Oil Price Collapse
- 2020 COVID Market Shock
- 2022 Energy Market Disruption

Observation:

Oil prices demonstrate strong sensitivity to macroeconomic and geopolitical disruptions.

---

# Statistical Preparation

## Log Transformation

Variance stabilization techniques were applied.

Purpose:

- Stabilize variance
- Improve statistical assumptions
- Improve forecasting readiness

---

## Rolling Statistics Analysis

Rolling mean and rolling standard deviation were analyzed.

Observations:

- Mean behavior changes over time
- Variability changes across historical periods
- Trend patterns remain visible

Conclusion:

The historical Brent oil price series remained non-stationary.

---

## Augmented Dickey-Fuller (ADF) Test

### Before Differencing

Result:

- p-value = 0.5988

Interpretation:

The series remained non-stationary.

---

## First Differencing

Trend removal techniques were applied.

Purpose:

- Improve stationarity
- Prepare data for ARIMA methodology

---

## Stationarity Validation After Differencing

Result:

- p-value = 5.02 × 10^-21

Interpretation:

The transformed series achieved stationarity and became suitable for forecasting models.

---

# ARIMA Model Identification

## ACF Analysis

Observations:

- Significant spike at Lag 1
- Remaining lags largely within confidence bounds
- No strong seasonal pattern detected

Interpretation:

The ACF suggested the presence of a low-order Moving Average (MA) component.

## PACF Analysis

Observations:

- Significant spike at Lag 1
- Subsequent lags largely insignificant

Interpretation:

The PACF suggested the presence of a low-order AutoRegressive (AR) component.

---

# ARIMA Model Selection

Several candidate models were evaluated using Akaike Information Criterion (AIC).

| Model | AIC |
|---------|---------:|
| ARIMA(1,1,1) | -786.37 |
| ARIMA(2,1,1) | -787.98 |
| ARIMA(1,1,2) | -789.51 |
| ARIMA(2,1,2) | -787.52 |

Observation:

ARIMA(1,1,2) achieved the lowest AIC value.

Conclusion:

ARIMA(1,1,2) was selected as the final forecasting model.

---

# Forecast Model Development

The selected ARIMA(1,1,2) model was trained using the historical log-transformed Brent crude oil price series.

The model generated forecasts for the subsequent 12-month period along with confidence intervals.

---

# Model Diagnostics

## Coefficient Significance

All ARIMA model coefficients were statistically significant.

Interpretation:

The model successfully captured meaningful temporal relationships within historical oil prices.

## Residual Analysis

Ljung-Box Test Result:

- Prob(Q) = 0.98

Interpretation:

No significant autocorrelation remained in the residuals, indicating a good model fit.

---

# Forecast Interpretation

Observations:

- Forecast prices gradually declined across the 12-month horizon.
- Forecasts suggested normalization following elevated 2022 price levels.
- Confidence intervals widened over time, reflecting increasing uncertainty.

Interpretation:

The model indicated a gradual stabilization and decline in Brent crude oil prices following the 2022 energy market disruption.

---

# Forecast Validation

A comparison with actual market behavior showed that the model correctly predicted the overall downward direction of Brent oil prices during 2023.

Although forecasted values were slightly higher than actual market prices, the model successfully captured the trend reversal and general market movement.

---

# Key Findings

1. Brent oil prices demonstrate long-term upward movement.
2. Oil prices exhibit right-skewed distribution characteristics.
3. Structural breaks significantly influence market behavior.
4. Variance stabilization improves forecasting preparation.
5. The original series was non-stationary.
6. First-order differencing successfully achieved stationarity.
7. ACF and PACF analysis indicated low-order autoregressive and moving average behavior.
8. ARIMA(1,1,2) achieved the lowest AIC value among candidate models.
9. The forecasting model predicted a gradual decline in oil prices over the forecast horizon.
10. Forecast uncertainty increased as the prediction horizon extended further into the future.
11. The model successfully captured the overall downward direction observed in subsequent real-world oil prices.

---

# Current Project Status

Completed:

- Data Acquisition
- Data Cleaning
- Exploratory Data Analysis
- Log Transformation
- Stationarity Testing
- ACF Analysis
- PACF Analysis
- ARIMA Model Selection
- Forecast Model Development
- 12-Month Brent Oil Price Forecast
- Model Diagnostics
- Forecast Interpretation
