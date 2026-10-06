# Factory Energy Forecasting and Storage Scheduling Optimization

A data-driven energy management framework that combines **electricity demand forecasting, solar generation forecasting, uncertainty estimation, and battery scheduling optimization** to reduce industrial electricity costs and peak-demand risk.

## Overview

As factories increasingly adopt solar generation and battery storage systems, energy management is no longer limited to reducing total electricity consumption. Effective battery charging and discharging decisions must also consider time-of-use tariffs, contract capacity, renewable generation, and uncertain future demand.

This project develops a two-stage **forecasting-and-optimization framework** for industrial energy management. Machine learning models are first used to forecast factory electricity demand and solar generation, and the predictions are then incorporated into a hierarchical Mixed-Integer Linear Programming (MILP) model to determine optimal battery schedules.

## Data

Two public energy datasets were used:

- **Steel Industry Energy Consumption** — 365 days of factory electricity consumption data recorded every 15 minutes
- **Renewable Power Generation and Weather Conditions** — solar generation and weather observations from 2017 to 2022

Feature engineering included:

- Lagged demand and generation features
- Rolling mean and volatility measures
- Cyclical time encoding
- Time-of-use tariff indicators
- Weather variables
- Solar-position and clear-sky related features

Time-series splitting and expanding-window validation were used to avoid data leakage.

## Forecasting

### Electricity Demand Forecasting

**XGBoost** was used to forecast factory electricity demand, with hyperparameters tuned through **Bayesian Optimization using Optuna**.

The optimized model achieved:

- **MAPE:** 15.00%
- **MAE:** 4.34 kWh
- **RMSE:** 9.26 kWh

A 90th-percentile quantile model was also trained to provide a conservative upper bound for high-load risk, achieving **90.88% empirical coverage**.

### Solar Generation Forecasting

Solar generation was predicted using weather, temporal, historical generation, and physical solar-position features.

The optimized XGBoost model achieved:

- **Test MAPE:** 36.10%
- **R²:** 0.8599
- **RMSE:** 452.82 Wh

For high-generation periods (2,000–5,000 Wh), MAPE decreased to **14.68%**.

A 10th-percentile quantile model was additionally used to provide a conservative lower bound for solar generation, with **89.07% empirical coverage**.

## Optimization Framework

The forecasting outputs were integrated into a hierarchical battery energy management system.

### Day-Ahead Scheduling

A **24-hour MILP model** determines the next day's battery State-of-Charge (SOC) reference trajectory using hourly resolution.

### Real-Time Scheduling

A rolling short-term optimization is performed every **15 minutes** over a 6-hour horizon to adjust battery charging and discharging decisions based on updated forecasts.

The optimization objective considers:

- Electricity purchase cost
- Time-of-use tariffs
- Contract-capacity penalties
- Peak demand
- Battery degradation
- Renewable-energy curtailment
- SOC constraints
- Charging and discharging power limits

This hierarchical design combines long-term planning with short-term flexibility while continuously adapting to forecast errors.

## Results

The proposed energy management system was evaluated against five rule-based baseline strategies.

For July 2018, the hierarchical EMS reduced total electricity cost from **NT$491,998** under the no-battery baseline to **NT$347,832**, corresponding to an approximately **29% reduction**.

The system also outperformed conventional rule-based strategies by strategically storing solar energy and shifting its use toward high-price peak periods.

The results demonstrate that integrating **forecasting, uncertainty estimation, and optimization** can provide greater economic value than independently optimizing prediction accuracy or applying fixed battery control rules.

## Repository Structure

```text
Manufacturing-Data-Science/
├── Factory-Power-Scheduling-Report.pdf   # Full project report
├── Factory-Power-Scheduling-Slides.pdf   # Final presentation slides
└── README.md
```

## Tech Stack

`Python` · `XGBoost` · `Optuna` · `Bayesian Optimization` · `SHAP` · `pvlib` · `MILP` · `Time Series Forecasting` · `Quantile Regression`

## Project Context

**Manufacturing Data Science, National Taiwan University**  
Team Project · Energy Analytics · Time Series Forecasting · Optimization · Industrial Data Science
