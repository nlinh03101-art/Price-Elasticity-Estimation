
# Price Elasticity Estimation

**Author:** Ngoc Linh Dao  
**Date:** January 17, 2024  
**Language:** R  
**Type:** Econometrics / Applied Regression Analysis  

---

## Overview
This case study estimates **price and income elasticities** for chicken consumption using a **log-log Ordinary Least Squares (OLS)** model.  
The project demonstrates both **theoretical understanding** and **empirical application** of elasticity estimation in macroeconomic data.

---

## Model Specification

\
`log(Y) = β₀ + β₁·log(income) + β₂·log(pchick) + β₃·log(pbeef) + β₄·log(ppork) + u`

Where:

| Variable | Description |
|-----------|--------------|
| `consum` | Chicken consumption (lb per capita) |
| `income` | Disposable income |
| `pchick` | Price of chicken |
| `pbeef` | Price of beef |
| `ppork` | Price of pork |

---

## Tasks & Methods

1. **Exploratory Visualization**  
   - Scatter plots on original and log-log scales  
   - Detection of exponential and proportional relationships  

2. **Model Estimation (OLS)**  
   - Regression fit using `lm()`  
   - Computation of \( R^2 \), Adjusted \( R^2 \), TSS, RSS, and SSR  

3. **Hypothesis Testing**  
   - **t-tests:** significance of individual coefficients  
   - **F-tests:** joint significance of multiple variables  
   - Manual and function-based verification (`linearHypothesis` from `{car}`)

4. **Interpretation**  
   - Elasticity interpretation for each coefficient  
   - Economic meaning of substitution effects between meats  

5. **Confidence Interval & Prediction**  
   - 99% confidence interval for income elasticity  
   - Forecasting demand under specific price/income values  

---

## Key Results

| Variable | Coefficient | Interpretation |
|-----------|--------------|----------------|
| log(income) | 0.3426 | 1% ↑ income → 0.34% ↑ demand |
| log(pchick) | -0.5046 | 1% ↑ price of chicken → 0.50% ↓ demand |
| log(ppork) | 0.1486 | Substitution effect: ↑ pork price → ↑ chicken demand |
| log(pbeef) | 0.0911 | Slight positive substitution effect |

- \( R^2 = 0.985 \), Adjusted \( R^2 = 0.982 \)
- F-statistic = 249.93, p-value < 0.001  
- Model strongly significant at the 1% level.

---

## Interpretation Summary

- **Income elasticity**: positive and significant → chicken is a normal good.  
- **Own-price elasticity**: negative and significant → demand decreases as price rises.  
- **Cross-price elasticities**: small but positive → beef/pork act as substitutes.  
- **Overall model fit**: excellent, consistent with demand theory.

---

## Tools & Packages
- `tidyverse`
- `car`
- `carData`
- `ggplot2`
- `dplyr`
- `stats`

---

## 💡 Learnings
- Interpreting log-log models as elasticity estimators  
- Using t- and F-tests for hypothesis testing  
- Manual verification of regression decomposition  
- Assessing statistical vs. economic significance  

---

## 📂 Repository Structure
├── price-elasticity-estimation.Rmd

├── chicken.csv

├── README.md

└── output/

└── price-elasticity-estimation.html
