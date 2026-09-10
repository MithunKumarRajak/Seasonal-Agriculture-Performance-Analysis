# Seasonal Agriculture Performance Analysis

### VOIS AICTE Batch1 - Major Project (2026–27)

---

## Overview

An end-to-end data analysis project examining how agricultural performance
varies across three Indian farming seasons - **Kharif**, **Rabi**, and **Zaid** -
across 8 major states. The study covers crop yields, farm economics, water usage,
nutrient application, pest/disease risk, and machine learning-based predictions.

**Dataset:** 4,000 farm records | 28 features | 8 Indian states | 3 seasons

---

## Project Structure

```
Seasonal-Agriculture-Performance-Analysis/
│
├── Seasonal_Agriculture_Performance_Analysis.ipynb   ← Main Notebook
├── README.md
│
└── figures/                         ← Pre-generated charts (10 plots)
    ├── seasonal_environmental_profiles.png
    ├── crop_distribution_by_season.png
    ├── yield_distribution_seasons.png
    ├── economic_performance_seasons.png
    ├── irrigation_efficiency_matrix.png
    ├── npk_fertilizer_dynamics.png
    ├── disease_pest_risk_heatmap.png
    ├── state_seasonal_resilience_map.png
    ├── clustering_farm_archetypes.png
    └── feature_importance_yield_profit.png
```

> **Note:** Place `seasonal_agriculture_data.csv` in the parent folder
> (`VOIS - Data Analysis/`) before running the notebook.

---

## How to Run

1. Open `Seasonal_Agriculture_Performance_Analysis.ipynb` in **VS Code** or **Jupyter**
2. Select **Python 3.11** kernel
3. Click **Run All**

### Required Libraries

```
numpy  pandas  matplotlib  seaborn  scipy  scikit-learn
```

---

## Notebook Sections

| # | Section |
| --- | --- |
| 1 | Importing Libraries |
| 2 | Loading the Dataset |
| 3 | Checking Data Quality |
| 4 | Data Cleaning |
| 5 | Feature Engineering |
| 6 | Seasonal Environmental Profiles |
| 7 | Crop Distribution by Season |
| 8 | Yield Analysis |
| 9 | Economic Performance |
| 10 | Water and Fertilizer Usage |
| 11 | Disease and Pest Risk Analysis |
| 12 | State-wise Performance |
| 13 | Statistical Tests |
| 14 | Predicting Yield (Random Forest) |
| 15 | Predicting Profit (Random Forest) |
| 16 | Farm Clustering (K-Means + PCA) |
| 17 | Final Summary & Conclusions |

---

## Key Results

| Season | Avg Yield (T/Ha) | Avg Profit (₹) | % Profitable | Avg Rainfall (mm) |
| --- | --- | --- | --- | --- |
| Kharif | 5.63 | 1,78,914 | 57.8% | 852 |
| Rabi | 5.09 | 87,689 | 48.9% | 436 |
| Zaid | 4.63 | −24,804 | 35.5% | 299 |

- All seasonal differences significant at **p < 0.001** (Kruskal-Wallis test)
- Yield prediction: **R² = 0.962** | Profit prediction: **R² = 0.869**

---

*VOIS AICTE Batch1 | 2026–2027 | Data Science Major Project*
