# README --- Brent Crude Oil Price Forecasting using Time Series Analysis

## Project Overview

This project aims to forecast Brent crude oil prices for the next 12
months using statistical time series forecasting techniques in Python.

## Dataset Information

### Dataset Details

**Dataset Title:** Brent Oil Prices

**Source:** Kaggle

**URL:** https://www.kaggle.com/datasets/mabusalah/brent-oil-prices

### Original Dataset Structure

Original dataset dimensions:

-   9011 observations
-   2 variables

Variables:

-   Date
-   Price

Dataset characteristics:

-   Historical Brent crude oil prices
-   Daily observations
-   Long historical coverage period
-   Suitable for time series forecasting applications

------------------------------------------------------------------------

## Methodology Overview

The project follows a structured forecasting pipeline:

1.  Data Acquisition
2.  Data Cleaning and Preparation
3.  Exploratory Data Analysis (EDA)
4.  Log Transformation
5.  Stationarity Testing
6.  Differencing
7.  ARIMA / SARIMA Model Development
8.  Forecast Generation

Current Progress:

Completed:

-   Data Acquisition
-   Data Cleaning
-   Exploratory Data Analysis
-   Stationarity Analysis

Pending:

-   ARIMA / SARIMA Modeling
-   Forecast Generation
-   Model Evaluation

------------------------------------------------------------------------

# Phase 1 --- Data Acquisition and Preparation

## Data Preparation Methods

Several preprocessing steps were performed to prepare the dataset for
forecasting.

### Date Processing

Date values were converted into time-series compatible format.

Purpose:

-   Enable temporal analysis
-   Support forecasting methodology

### Chronological Ordering

Historical observations were ordered chronologically.

Purpose:

-   Maintain time-series integrity

### Time Index Construction

The date field was assigned as the time index.

Purpose:

-   Enable resampling
-   Support forecasting workflows

### Missing Data Assessment

The dataset was evaluated for:

-   Missing values
-   Temporal gaps
-   Irregular spacing

Observation:

Historical oil market data naturally contains irregular spacing due to
weekends and market closures.

------------------------------------------------------------------------

## Monthly Aggregation

The forecasting objective targets monthly oil price prediction.

Daily observations were aggregated into monthly averages.

Monthly dataset dimensions:

-   427 observations
-   1 variable

Purpose:

-   Reduce daily market noise
-   Improve forecasting stability
-   Align analysis directly with business objectives

------------------------------------------------------------------------

# Exploratory Data Analysis (EDA)

Several visual analyses were performed to understand oil price behavior.

## Historical Trend Analysis

Observations:

-   Brent crude oil prices demonstrate a long-term increasing trend
-   Market fluctuations occur throughout historical periods
-   Significant price disruptions appear during major economic events

Interpretation:

Oil market behavior reflects:

-   Global economic activity
-   Supply-demand changes
-   Geopolitical influences

Energy Economics Perspective:

For hydrocarbon-dependent economies such as Qatar, oil price
fluctuations directly influence national revenue planning and
economic decision-making.

------------------------------------------------------------------------

## Distribution Analysis

Observations:

-   Oil prices exhibit right-skewed behavior
-   Lower price levels occur more frequently
-   High-price periods occur less frequently

Interpretation:

Oil price distributions are not normally distributed.

Implication:

Variance stabilization techniques are necessary before statistical
forecasting.

------------------------------------------------------------------------

## Structural Break Analysis

Major economic disruptions were identified through structural-break
visualization.

Events examined:

-   1990 Gulf War
-   2008 Financial Crisis
-   2014 Oil Price Collapse
-   2020 COVID Market Shock
-   2022 Energy Market Disruption

Observation:

Oil prices demonstrate strong sensitivity to macroeconomic and
geopolitical disruptions.

------------------------------------------------------------------------

# Statistical Preparation

## Log Transformation

Variance stabilization techniques were applied.

Purpose:

-   Stabilize variance
-   Improve statistical assumptions
-   Improve forecasting readiness

------------------------------------------------------------------------

## Rolling Statistics Analysis

Rolling mean and rolling standard deviation were analyzed.

Observations:

-   Mean behavior changes over time
-   Variability changes across historical periods
-   Trend patterns remain visible

Conclusion:

The historical Brent oil price series remained non-stationary.

------------------------------------------------------------------------

## Augmented Dickey-Fuller (ADF) Test

Stationarity testing was performed.

### Before Differencing

Result:

-   p-value = 0.5988

Interpretation:

The series remained non-stationary.

------------------------------------------------------------------------

## First Differencing

Trend removal techniques were applied.

Purpose:

-   Improve stationarity
-   Prepare data for ARIMA methodology

------------------------------------------------------------------------

## Stationarity Validation After Differencing

Result:

-   p-value = 5.02 × 10\^-21

Interpretation:

The transformed series achieved stationarity and became suitable for
forecasting models.

------------------------------------------------------------------------

# Key Findings

Findings:

1.  Brent oil prices demonstrate long-term upward movement.
2.  Oil prices exhibit right-skewed distribution characteristics.
3.  Structural breaks significantly influence market behavior.
4.  Variance stabilization improves forecasting preparation.
5.  The original series was non-stationary.
6.  First-order differencing successfully achieved stationarity.

------------------------------------------------------------------------

# Current Project Status

Completed:

-   Data Acquisition
-   Data Cleaning
-   Exploratory Data Analysis
-   Log Transformation
-   Stationarity Testing

Next Steps:

-   ACF / PACF Analysis
-   ARIMA / SARIMA Order Selection
-   Forecast Model Development
-   12-Month Brent Oil Price Forecast
-   Model Evaluation

------------------------------------------------------------------------
