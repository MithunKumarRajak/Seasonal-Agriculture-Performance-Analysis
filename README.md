# Seasonal Agriculture Performance Analysis

### VOIS AICTE Data Analysis -  Major Project

## Overview

An agricultural data analytics study investigating how farm performance, resource consumption, risk exposure, and economic outcomes vary across three primary Indian cropping seasons: **Kharif** (monsoon), **Rabi** (winter), and **Zaid** (summer).

The project covers comprehensive exploratory data analysis (EDA), data cleaning with mathematical value reconstruction, multi-dimensional feature engineering, non-parametric statistical hypothesis testing, machine learning regression models for yield and profit prediction, and unsupervised clustering of farm operational archetypes.

* **Dataset Size:** 4,000 farm records | 28 primary attributes (expanded to 37 features)
* **Geographic Scope:** 8 Indian states (*Andhra Pradesh, Gujarat, Karnataka, Madhya Pradesh, Maharashtra, Punjab, Tamil Nadu, Telangana*)
* **Seasons Analyzed:** Kharif (1,779 farms), Rabi (1,627 farms), Zaid (594 farms)
* **Crops Analyzed:** Rice, Wheat, Maize, Cotton, Pulses, Groundnut, Chilli, Sugarcane

---

## Current Folder Structure

```
Seasonal-Agriculture-Performance-Analysis/
│
├── Seasonal_Agriculture_Performance_Analysis.ipynb   # Complete analysis notebook (cleaning, EDA, ML, stats)
├── seasonal_agriculture_data.csv                     # Primary dataset (4,000 records, 28 attributes)
├── project_problem_statement.pdf                     # VOIS AICTE project brief & guidelines
├── README.md                                         # Project documentation & findings report
└── .gitignore                                        # Git ignore rules for Python & Jupyter artifacts
```

### File Descriptions

* **`Seasonal_Agriculture_Performance_Analysis.ipynb`**: The self-contained primary deliverable. Formatted with beginner-friendly, modular cells (averaging 5–6 lines of code per cell) and natural commentary. All visualizations, summary tables, statistical test outputs, and machine learning evaluations render directly inline.
* **`seasonal_agriculture_data.csv`**: The benchmark agricultural dataset placed directly in the project directory for out-of-the-box execution.
* **`project_problem_statement.pdf`**: The official problem statement and evaluation rubric provided for the VOIS AICTE internship program.
* **`README.md`**: Project overview, folder layout, execution guide, and analytical results.
* **`.gitignore`**: Excludes transient caches (`__pycache__`, `.ipynb_checkpoints`, virtual environment directories).

---

## How to Run

The notebook is configured to detect and load `seasonal_agriculture_data.csv` directly from the local folder without requiring any path configuration.

### 1. Prerequisites & Environment

Ensure you have Python 3.9+ or Python 3.11 installed along with the standard data science stack:

```bash
pip install numpy pandas matplotlib seaborn scipy scikit-learn
```

### 2. Running in VS Code or Jupyter Lab

1. Open the project folder (`Seasonal-Agriculture-Performance-Analysis`) in **VS Code** or launch **Jupyter Lab / Notebook**.
2. Open `Seasonal_Agriculture_Performance_Analysis.ipynb`.
3. Select the active Python kernel (e.g., Python 3.11).
4. Click **Run All** (or execute cells sequentially).

---

## Notebook Structure & Workflow

The notebook contains **102 cells** (83 modular code cells and 19 markdown headers) organized into 17 analytical sections:

| # | Section | Description |
| :----------: | :-------------------------------- | :---------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **1** | Importing Libraries | Loading NumPy, Pandas, Matplotlib, Seaborn, SciPy, and Scikit-Learn |
| **2** | Loading Dataset | Loading`seasonal_agriculture_data.csv` with automatic path resolution |
| **3** | Checking Data Quality | Auditing null values, dimensions, data types, and initial anomalies |
| **4** | Data Cleaning | Imputing missing values via group medians; exact mathematical reconstruction of missing yields (`Production / Area`) |
| **5** | Feature Engineering | Creating economic ratios (`Profit_Margin_pct`, `Cost_per_Ha`, `Revenue_per_Ha`, `ROI`), `Water_Productivity`, `NPK_Total`, and `Pest_Risk_Category` |
| **6** | Seasonal Environmental Profiles | Comparing rainfall, temperature, humidity, sunlight, soil pH, and soil moisture across seasons |
| **7** | Crop Distribution by Season | Visualizing crop portfolio shares and production across Kharif, Rabi, and Zaid |
| **8** | Yield Analysis | Distribution of yields (T/Ha), violin plots, crop-season performance matrices |
| **9** | Economic Performance | Revenue, cost structures, net profit margins, and profitability percentages across seasons |
| **10** | Water & Fertilizer Usage | Irrigation methods (Drip, Sprinkler, Flood, Rainfed), water efficiency, and NPK nutrient dynamics |
| **11** | Disease & Pest Risk Analysis | Correlation of pest risks with rainfall ($r = 0.62$), humidity ($r = 0.55$), and seasonal disease incidence |
| **12** | State-wise Performance | Cross-state benchmarking of seasonal resilience and profit margins across 8 states |
| **13** | Statistical Hypothesis Testing | One-way ANOVA, Kruskal-Wallis tests, Chi-Square independence tests, and Dunn's post-hoc tests |
| **14** | Predicting Yield (Random Forest) | Machine learning regression for crop yield prediction with evaluation metrics ($R^2$, MAE, RMSE) |
| **15** | Predicting Profit (Random Forest) | Machine learning regression for farm net profit prediction and feature importance rankings |
| **16** | Farm Clustering (K-Means + PCA) | Unsupervised grouping of farms into operational archetypes with 2D PCA projection |
| **17** | Summary & Conclusions | Synthesis of findings, strategic recommendations for seasonal agricultural planning |

---

## Key Results & Analytical Findings

### 1. Seasonal Performance Summary

| Metric                          | Kharif (Monsoon) |  Rabi (Winter)  |  Zaid (Summer)  | Significance |
| :------------------------------ | :--------------: | :--------------: | :--------------: | :-----------: |
| **Farms Analyzed**        |  1,779 (44.5%)  |  1,627 (40.7%)  |   594 (14.8%)   |       -       |
| **Avg Rainfall (mm)**     |     852.3 mm     |     435.9 mm     |     298.9 mm     | $p < 0.001$ |
| **Avg Temperature (°C)** |     28.2 °C     |     20.4 °C     |     34.6 °C     | $p < 0.001$ |
| **Avg Yield (Tonnes/Ha)** |       5.63       |       5.09       |       4.63       | $p < 0.001$ |
| **Avg Net Profit (₹)**   |    ₹1,78,914    |     ₹87,689     |    −₹24,804    | $p < 0.001$ |
| **Farms Profitable (%)**  |      57.8%      |      48.9%      |      35.5%      | $p < 0.001$ |
| **Avg Pest Risk Index**   |   54.5% (High)   | 40.5% (Moderate) | 38.2% (Moderate) | $p < 0.001$ |

### 2. Statistical Hypothesis Tests

* **Kruskal-Wallis Tests**: Highly statistically significant differences across seasons for Yield ($H = 70.59, p < 0.001$), Profit ($H = 101.93, p < 0.001$), Rainfall ($H = 2598.94, p < 0.001$), Water Efficiency ($H = 56.81, p < 0.001$), and Pest Risk ($H = 1430.91, p < 0.001$).
* **Pairwise Post-Hoc Tests**: Pairwise Mann-Whitney U tests confirmed that Kharif vs. Rabi, Kharif vs. Zaid, and Rabi vs. Zaid are all mutually distinct ($p < 0.001$).
* **Chi-Square Independence**: Crop selection ($\chi^2 = 13.93, p = 0.455$) and irrigation method ($\chi^2 = 3.51, p = 0.742$) show no strict seasonal dependency, showing that farmer infrastructure limitations often dictate practice rather than seasonal optimization.

### 3. Machine Learning Models

* **Yield Prediction (Random Forest Regressor)**:
  * **$R^2$ Score:** `0.962` (explaining 96.2% of variance in yield)
  * **MAE:** `0.770` Tonnes/Ha
  * **RMSE:** `2.701` Tonnes/Ha
* **Profit Prediction (Random Forest Regressor)**:
  * **$R^2$ Score:** `0.869` (explaining 86.9% of variance in net profit)
  * **Key Predictors:** Production Volume, Total Farm Area, Market Price Realization, Water Utilization, and Nitrogen application rate.
* **Farm Clustering (K-Means + PCA)**:
  * Optimal silhouette score identifies distinct operational tiers: high-efficiency capital-intensive farms vs. input-constrained / weather-vulnerable holdings.

---

## Core Insights & Recommendations

1. **Mitigate Zaid Season Economic Losses**:
   * Zaid suffers negative average profitability (−₹24,804) due to high irrigation pumping costs, excessive evaporation, and lower yields under thermal stress.
   * **Recommendation**: Transition Zaid cultivation towards micro-irrigation (Drip/Sprinkler) and drought-tolerant short-duration crops (pulses, summer oilseeds).
2. **Targeted Pest Management in Kharif**:
   * Kharif pest risk peaks at 54.5%, driven by high relative humidity ($r = 0.55$) and monsoon rainfall ($r = 0.62$).
   * **Recommendation**: Deploy early-warning disease monitoring and synchronized prophylactic biocontrol during high-humidity periods.
3. **Enhance Water Productivity**:
   * Farms utilizing drip irrigation achieved up to 40% higher water productivity ($₹/\text{m}^3$) compared to traditional flood irrigation.
   * **Recommendation**: State-level subsidies should incentivize solar-powered drip kits in moisture-deficient districts.

---

*VOIS AICTE Intership  | Data Analytics Major Project*
