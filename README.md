# FMCG Demand Forecasting — Time Series vs Machine Learning

## 📌 Project Overview

This project investigates demand forecasting for an FMCG company using both classical time series methods and modern machine learning models.

The objective is to compare forecasting accuracy across different modeling paradigms and evaluate the impact of exogenous business drivers such as:

- Price
- Promotions
- Stock availability
- Delivery time
- Calendar effects

The study follows a research-grade evaluation framework with time-based splits and rolling cross-validation.

---

## 📊 Dataset

- Period: Jan 2022 – Dec 2024
- Observations: 190,000+
- 30 SKUs
- 14 brands
- 3 regions
- 3 sales channels

Target variable: `units_sold`

---

## 🔧 Feature Engineering

Created features include:

- Calendar features (day of week, month, week number)
- Lag features (1, 7, 14 days)
- Rolling statistics (7-day mean & std)
- Price and promotion lags
- Operational features (stock, delivery)

All features are built using strictly time-safe transformations to prevent data leakage.

---

## 🤖 Models Implemented

### Time Series Models
1. SARIMA (Seasonal ARIMA)
2. Prophet

### Machine Learning Models
3. CatBoost (Global model)
4. LightGBM (Global model)

---

## 📈 Evaluation Framework

- 90-day holdout split
- Rolling-origin time series cross-validation
- Aggregated and SKU-level metrics
- Metrics:
  - MAE
  - RMSE
  - MAPE

---

## 🏆 Final Results (Aggregated Forecast)

| Model      | Type              | Aggregated MAPE | Aggregated RMSE |
|------------|------------------|-----------------|-----------------|
| LightGBM   | Machine Learning | **2.70%** | 118.75 |
| CatBoost   | Machine Learning | 2.76% | 120.75 |
| Prophet    | Time Series      | 4.69% | 223.15 |
| SARIMA     | Time Series      | 8.19% | 335.24 |

---

## 🔬 Key Findings

- Machine learning models outperform classical time series approaches.
- Including price, promotion and stock variables reduces error by ~67% compared to SARIMA.
- Boosting models demonstrate strong stability across rolling windows.
- Prophet improves over SARIMA but fails to capture exogenous demand drivers.

---

## 🧠 Interpretation

Classical time series models rely solely on historical patterns.

Machine learning models incorporate structural business drivers, making them better suited for FMCG environments where demand is strongly influenced by pricing and promotional dynamics.

---

## 📁 Project Structure
fmcg-demand-forecasting/
│
├── notebooks/
│ ├── 01_data_exploration.ipynb
│ ├── 02_feature_engineering.ipynb
│ ├── 03_baseline_model.ipynb
│ ├── 04_ml_model.ipynb
│ ├── 05_sarima_model.ipynb
│ ├── 06_lightgbm_model.ipynb
│ ├── 08_time_series_cv.ipynb
│ └── 09_model_comparison.ipynb
│
├── data/
│ └── processed/
│
├── README.md
└── .gitignore


---

## 🚀 Reproducibility

1. Create virtual environment
2. Install dependencies
3. Run notebooks sequentially:
   - EDA
   - Feature engineering
   - Modeling
   - Comparison

---

## 📌 Conclusion

The study demonstrates that global ML models with engineered demand drivers significantly outperform classical time series models in FMCG forecasting tasks.

This supports the hypothesis that demand prediction in retail environments benefits from feature-rich supervised learning frameworks.

