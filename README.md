
# Cairo Real Estate Pricing

**Project:** Data-driven pricing tool for 2–3 bedroom apartments in New Cairo, Egypt  
**Author:** Shahd Yasser Elsayed
**Date:** 2025  

---

## Project Overview

PropMatch Egypt has recently hired junior property consultants who struggle to price residential apartments accurately. Incorrect pricing leads to properties either staying unsold for months or being undersold.  

This project builds a **machine learning pricing tool** to support junior agents, focusing on **2–3 bedroom apartments in New Cairo**.

The model predicts apartment prices within ±EGP 150,000 accuracy, providing actionable insights to improve sales conversion rates.

---

## Dataset

- **Size:** 3,500 listings from 2023–2025  
- **Core features:** `listing_id`, `price_egp`, `area_sqm`, `bedrooms`, `bathrooms`, `floor_number`, `building_age_years`  
- **Location:** `district`, `compound_name`, distances to key landmarks  
- **Property characteristics:** `finishing_type`, `has_balcony`, `has_parking`, `has_security`, `has_amenities`, `view_type`  
- **Market context:** `listing_date`, `days_on_market`, `seller_type`, `is_negotiable`  



## Methodology

1. **Data Cleaning & EDA**  
   - Filtered for 2–3 bedroom apartments  
   - Handled missing values, outliers, and categorical encodings  

2. **Feature Engineering**  
   - Derived features: `price_per_sqm`, `price_per_bedroom`  
   - Compound and neighborhood indicators  
   - Log transformations for skewed variables  

3. **Model Development**  
   - Models compared: Linear Regression, Ridge, Lasso, Random Forest, XGBoost  
   - Best model: **Tuned XGBoost pipeline**  
   - Optional ensemble with Random Forest for improved performance  

4. **Evaluation**  
   - Metrics: MAE, RMSE, R²  
   - Bootstrap confidence intervals for MAE  
   - High-error listing analysis (> EGP 150,000)  
   - SHAP plots for feature importance  

---

## Key Results

- **XGBoost performance:**  
  - MAE: 1,727 EGP  
  - RMSE: 13,741 EGP  
  - R²: 0.9998  
- Only 3 out of 1,820 listings had errors > EGP 150,000  
- Saved predictions, high-error listings, and district-level error counts for business insights  

---

## How to Use

1. Clone the repository:  
```bash
git clone https://github.com/shahdyasserelsayed/Cairo_Real_Estate_Pricing.git

2. Install dependencies:

```bash
pip install -r requirements.txt
```

3. Open notebooks in order:

   * `01_data_exploration.ipynb` → cleaning & EDA
   * `02_model_development.ipynb` → modeling
   * `03_refinement.ipynb` → prediction & analysis

4. Use `xgb_tuned_advanced_pipe.pkl` for making price predictions on new apartments.

---

## Business Impact

* Improves pricing accuracy for junior agents
* Reduces high-error listings, shortening time on market
* Provides actionable insights for negotiation and pricing strategies
