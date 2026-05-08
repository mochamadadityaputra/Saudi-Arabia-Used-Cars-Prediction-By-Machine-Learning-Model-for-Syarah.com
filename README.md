# 🚗 Used Car Price Prediction for Syarah.com — Saudi Arabia

> Building a machine learning regression model to predict used car prices and support transparent, data-driven pricing for one of Saudi Arabia's largest automotive marketplaces.

**Solo Project** | Purwadhika Digital Technology School — JCDSOL-015
Author: Mochamad Aditya Putra Yudha Kusuma

---

## 📊 Dashboard Preview

### Power BI
![Power BI Dashboard](ADD_YOUR_POWERBI_SCREENSHOT_HERE.png)
*Take a screenshot of your Power BI dashboard and upload it to this repo*

### Tableau
![Tableau Dashboard](ADD_YOUR_TABLEAU_SCREENSHOT_HERE.png)
📎 [View Interactive Tableau Dashboard](https://public.tableau.com/app/profile/aditya.putra5948/viz/SyarahDash/Overview?publish=yes)

---

## 📋 Table of Contents

- [Problem Statement](#problem-statement)
- [Project Objectives](#project-objectives)
- [Dataset Overview](#dataset-overview)
- [Methodology](#methodology)
- [Model Results](#model-results)
- [Key Findings & Feature Importance](#key-findings--feature-importance)
- [Recommendations](#recommendations)
- [Tech Stack](#tech-stack)
- [Repository Structure](#repository-structure)
- [Links](#links)

---

## Problem Statement

The Saudi Arabian used car market is one of the largest in the Middle East, driven by population growth, urbanisation, and the rise of digital platforms like Syarah.com. However, pricing in this market remains highly inconsistent — the same car can be listed at vastly different prices depending on the seller, region, and timing.

For a marketplace like Syarah.com, this pricing uncertainty creates friction for both buyers and sellers: buyers struggle to assess fair value, while sellers risk either underpricing their vehicle or losing customers to competitors with more transparent pricing.

This project builds a machine learning model to predict used car prices based on vehicle attributes, enabling Syarah.com to offer data-driven price recommendations that improve transparency and trust across the platform.

**Key questions this project answers:**
1. What are the primary factors that drive used car prices in Saudi Arabia?
2. Can a machine learning model outperform a rule-based pricing baseline?
3. How accurately can the model estimate prices across the full range of vehicles listed on the platform?

---

## Project Objectives

- Develop a regression model that significantly outperforms the rule-based baseline (MAE: 55,230 SAR)
- Identify the key pricing drivers through rigorous EDA and feature importance analysis
- Reduce pricing uncertainty to a practically useful error margin for marketplace decision-making
- Deliver findings through interactive dashboards for real-time price support

---

## Dataset Overview

| Item | Detail |
|---|---|
| Source | Purwadhika (collected from Syarah.com) |
| Raw records | 5,624 rows |
| Cleaned records | 3,700 rows (with outliers removed for modeling) |
| Target variable | `Price` (SAR — Saudi Riyal) |
| Mean price | 53,074 SAR |
| Median price | 36,500 SAR |

### Data Dictionary

| Feature | Description |
|---|---|
| `Type` | Car model name |
| `Region` | Region where the car is listed for sale |
| `Make` | Car manufacturer / brand |
| `Gear_Type` | Transmission type |
| `Origin` | Country of origin |
| `Options` | Feature package level (Standard, Full, etc.) |
| `Year` | Year of manufacture |
| `Engine_Size` | Engine displacement size |
| `Mileage` | Total distance travelled |
| `Negotiable` | Whether price is negotiable (True if listed at 0) |
| `Price` | Listed price in SAR (target variable) |

---

## Methodology

### 1. Data Cleaning
- Handled missing values, duplicates, anomalies, and outliers
- Divided dataset into two versions: with outliers and without outliers
- Selected the **without-outliers dataset** for modeling after comparison — showed more robust and generalizable results across 3,700 cleaned records

### 2. Exploratory Data Analysis (EDA)
- Analyzed price distribution across brands, regions, engine sizes, and years
- Identified key pricing patterns and correlations with the target variable
- Visualized market segmentation to understand where price variance is highest

### 3. Baseline Model (Rule-Based)
- Built a rule-based pricing model as the benchmark
- Result: **MAE of 55,230 SAR** — established as the target to beat

### 4. Model Comparison
Compared 8 regression models on the cleaned dataset:

| Model | Notes |
|---|---|
| Linear Regression | Baseline ML model |
| Decision Tree Regressor | High variance, prone to overfitting |
| KNeighbors Regressor | Moderate performance |
| Voting Regressor | Ensemble of weak learners |
| Stacking Regressor | Meta-learner approach |
| Random Forest Regressor | Strong performance |
| Gradient Boosting Regressor | Strong performance |
| **XGBoost Regressor** | **Best performer ✅** |

### 5. Top 5 Model Comparison (Key Metrics)

| Model | MAE | RMSE | R² |
|---|---|---|---|
| Gradient Boosting | ~13,500 | ~21,000 | ~0.71 |
| Random Forest | ~13,200 | ~20,500 | ~0.72 |
| Stacking Regressor | ~13,100 | ~20,200 | ~0.73 |
| Voting Regressor | ~13,000 | ~20,000 | ~0.73 |
| **XGBoost (pre-tuning)** | **12,874** | **19,454** | **0.741** ✅ |

### 6. Hyperparameter Tuning
Applied **Bayesian Optimization** to XGBoost:

| Metric | Before Tuning | After Tuning | Improvement |
|---|---|---|---|
| MAE | 12,874 SAR | **11,134 SAR** | ↓ 13.5% |
| RMSE | 19,454 SAR | **16,965 SAR** | ↓ 12.8% |
| R² | 0.741 | **0.803** | ↑ 8.4% |
| MAPE | 22.36% | **19.34%** | ↓ 3.02% |

### 7. Pipeline Architecture
The final model is a full ML pipeline with the following preprocessing steps:

- **OneHotEncoder** — categorical features with few unique values (Gear_Type, Origin, Options)
- **BinaryEncoder** — high-cardinality categorical features (Type, Region, Make)
- **MinMaxScaler** — numerical features (Year, Engine_Size)
- **RobustScaler** — applied to Mileage to reduce sensitivity to outliers
- **XGBoost Regressor** — final prediction model with Bayesian-tuned hyperparameters

---

## Model Results

### Final Model Performance (XGBoost — after Bayesian Optimization)

| Metric | Value | Interpretation |
|---|---|---|
| MAE | **11,134 SAR** | Average prediction error per vehicle |
| RMSE | **16,965 SAR** | Error metric sensitive to large deviations |
| R² | **0.803** | Model explains 80.3% of price variance |
| MAPE | **19.34%** | Average percentage error across all predictions |

### vs. Rule-Based Baseline

| | Rule-Based Model | XGBoost (tuned) | Improvement |
|---|---|---|---|
| MAE | 55,230 SAR | **11,134 SAR** | **↓ 79.8%** |

The machine learning model reduced average pricing error by nearly **80%** compared to the conventional rule-based approach — from 55,230 SAR down to 11,134 SAR per vehicle.

---

## Key Findings & Feature Importance

The top factors driving used car prices in the Saudi market, in order of model importance:

1. **Engine Size** — the single most influential feature. Larger engines consistently command higher prices due to performance associations.
2. **Brand (Make)** — brand reputation is a major price driver. Premium and well-known brands significantly outprice lesser-known alternatives.
3. **Year of Manufacture** — newer cars price higher. Depreciation curves vary significantly by brand.
4. **Options Package** — cars with Standard options price noticeably lower than Full or Semi-Full packages.
5. **Mileage** — higher mileage reduces price, though the relationship is non-linear and brand-dependent.

**Key EDA insights:**
- Toyota, Kia, and GMC dominate the listing volume on Syarah.com
- Luxury brands (Land Rover, BMW, Mercedes) show the highest price variance — harder to predict accurately
- Region of listing has moderate influence — Riyadh and Jeddah listings tend to price slightly higher
- Negotiable listings (price = 0) were excluded as they represent incomplete data

---

## Recommendations

**For Syarah.com platform:**
- Deploy the model as a real-time price suggestion tool at the listing creation stage — sellers input specs, model returns a suggested price range (±11,134 SAR)
- Flag listings priced more than 2× the model's prediction for manual review — likely data entry errors or fraudulent listings
- Use feature importance insights to prompt sellers for the most price-relevant information first (engine size, brand, year, options)

**For pricing strategy:**
- Luxury segment (BMW, Land Rover, Mercedes) has the highest prediction error — consider a separate model or confidence interval for this segment
- Mileage-based discounting could be more systematically applied — data shows buyers respond predictably to mileage brackets
- Regional pricing differences suggest Syarah.com could introduce location-adjusted price recommendations

---

## Tech Stack

| Category | Tools |
|---|---|
| Language | Python |
| Data Manipulation | Pandas, NumPy |
| Visualization | Matplotlib, Seaborn |
| Machine Learning | Scikit-learn, XGBoost |
| Encoding | Category Encoders (BinaryEncoder) |
| Hyperparameter Tuning | Bayesian Optimization (Scikit-Optimize / Optuna) |
| BI & Dashboards | Power BI, Tableau |
| Model Saving | Pickle (.pkl) |
| Environment | Google Colab |
| Version Control | GitHub |

---

## Repository Structure

```
Saudi-Arabia-Used-Cars-Prediction/
│
├── Capstone_Project_Module_3.ipynb   # Main notebook
├── Capstone Project 3.pptx           # Project presentation
├── Syarah Dashboard PowerBI.pbix     # Power BI dashboard file
├── dashboard syarah.twb              # Tableau dashboard file
├── data_saudi_used_cars.csv          # Raw dataset
├── model.pkl                         # Saved tuned XGBoost model
└── README.md
```

---

## 🔗 Links

| Resource | Link |
|---|---|
| 📓 Notebook (Google Colab) | [Open Notebook](https://colab.research.google.com/drive/1RdpwL3b7nLN0UdwjHc1Bz6HkI11PRGq8?usp=sharing) |
| 📊 Power BI Dashboard | [View on Google Drive](https://drive.google.com/file/d/1YF5IkmE4Qmxt80h-HjN_EEf0Xvb7oLxD/view?usp=sharing) |
| 📈 Tableau Dashboard | [View on Tableau Public](https://public.tableau.com/app/profile/aditya.putra5948/viz/SyarahDash/Overview?publish=yes) |
| 🎤 Presentation (Video) | [Watch on Google Drive](https://drive.google.com/file/d/1ahSQW5Xpmf2x7eKzUYjKpu9ureNFBos4/view?usp=sharing) |
| 📑 Presentation (Slides) | [Open Slides](https://docs.google.com/presentation/d/1s94GgoHzMH4fj8A6eUXuosuQX68TXjr-/edit?usp=sharing) |
