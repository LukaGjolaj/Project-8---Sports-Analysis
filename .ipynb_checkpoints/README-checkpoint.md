# Project 8: Sports Analysis  
## Identifying Key Drivers of NBA Team Performance

**Date:** April 21, 2025  
**Course:** CMSE 202 Section 4  

---

## 1. Introduction

This project analyzes NBA team statistics from the 2021‑22 through 2024‑25 seasons to answer the question:  
> **What key team performance metrics can an NBA team focus on to maximize its chance to win the most games?**  

We also explore the drivers of offensive efficiency (Offensive Rating – ORTG).

Our workflow:
1. **Data collection** via `nba_api`  
2. **Feature engineering** (e.g., minutes‑weighted average height and wingspan)  
3. **Modeling**: compare Linear Regression and Random Forest  
4. **Statistical inference** with `statsmodels`  
5. **Model interpretation** using SHAP  

---

## 2. Dependencies

This project uses Python 3 and the following key libraries:  
- `pandas`  
- `numpy`  
- `matplotlib`  
- `seaborn`  
- `scikit-learn`  
- `statsmodels`  
- `shap`  
- `nba_api`  

---

## 3. File Structure

- **Project-8---Sports-Analysis/**  
  - **data/**  
    - **rawdata/**  
      - Raw seasonal API outputs & player measurements  
    - **cleandata/**  
      - Processed team & player CSVs  
  - **docs/**  
    - Documentation (reports, PDFs)  
  - **notebooks/**  
    - Jupyter notebooks for each step  
  - **report/**  
    - Final report assets (figures, slides)  
  - **.gitignore**  
  - **README.md**  
    - This overview  
  - **requirements.txt**  
    - Python dependencies  
  - **ProjectDiscussionAndPlanning.md**  

---

## 4. How to Run the Code

Run the notebooks in **sequence** from the `notebooks/` folder:

1. **`api.ipynb`**  
   - _Purpose:_ Fetch raw team stats & player minutes via `nba_api` (2021–2025)  
   - _Output:_ CSVs in `data/rawdata/`

2. **`combine_data.ipynb`**  
   - _Purpose:_ Clean raw data, impute missing values, compute weighted metrics  
   - _Input:_ `data/rawdata/`  
   - _Output:_ Cleaned CSVs in `data/cleandata/`; optional combined DataFrame

3. **`linear_regression.ipynb`**  
   - _Purpose:_  
     - Train Linear Regression models to predict **Wins** and **ORTG**  
     - Evaluate (R², MAE, RMSE)  
     - Generate OLS summaries via `statsmodels`  
     - Plot diagnostics (Actual vs. Predicted, Residuals)  
   - _Input:_ `data/cleandata/`

4. **`random_forest.ipynb`**  
   - _Purpose:_  
     - Train Random Forest regressors for **Wins** & **ORTG**  
     - Evaluate performance, extract feature importances  
     - Perform SHAP analysis (global bar plot & beeswarm)  
   - _Input:_ `data/cleandata/`  
   - _Output:_ SHAP plots saved to `report/figures/`

5. **`visualizations.ipynb`** 
   - _Purpose:_  
     - Create final visuals: correlation heatmap, model performance comparison  
   - _Input:_ Cleaned data + saved metrics from previous steps  
   - _Output:_ Figures for the report

> **Note:** If you have additional notebooks (e.g., `shot_chart.ipynb`), clarify their order or mark them as optional explorations.

---

## 5. Member Contributions

> _Replace the placeholder text below with each member’s actual tasks._

- **Luka Gjolaj**  
  - Led data collection via `nba_api`  
  - Performed initial cleaning and organization

- **Kevin Pham**  
  - Implemented Random Forest modeling & SHAP analysis  
  - Generated interpretation plots

- **Eric Grenadier**  
  - Integrated player measurement data  
  - Calculated weighted metrics  
  - Ran Linear Regression & OLS inference

- **Sahat**  
  - Conducted correlation analysis  
  - Contributed to feature selection and drafted report sections

- **Nate**  
  - Managed GitHub repository structure  
  - Finalized code documentation and created presentation slides
