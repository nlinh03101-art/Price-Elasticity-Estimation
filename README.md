# Price Elasticity Estimation: Log-Log OLS Demand Analysis

## Overview
This project estimates **price and income elasticities** for chicken demand using a **log-log Ordinary Least Squares (OLS)** model.  
The analysis explores how **income and relative meat prices** (chicken, beef, pork) influence consumption patterns, and evaluates statistical significance using both **t-tests** and **F-tests**.

---

## Project Summary
The dataset (`chicken.csv`) contains macroeconomic data on chicken consumption, income levels, and meat prices.  
The objective is to quantify how sensitive chicken demand is to changes in:
- **Income** (income elasticity)
- **Own price** (own-price elasticity)
- **Cross prices** of beef and pork (cross-price elasticities)

The model is specified as:

`log(Y) = β₀ + β₁·log(income) + β₂·log(pchick) + β₃·log(pbeef) + β₄·log(ppork) + u`

Elasticities are directly interpreted from the estimated coefficients due to the log-log specification.

---

## Key Results

| Variable | Coefficient | Interpretation |
|-----------|--------------|----------------|
| log(income) | 0.3426 | 1% ↑ income → 0.34% ↑ demand |
| log(pchick) | -0.5046 | 1% ↑ price of chicken → 0.50% ↓ demand |
| log(ppork) | 0.1486 | Substitution: ↑ pork price → ↑ chicken demand |
| log(pbeef) | 0.0911 | Slight positive substitution effect |

**Model Fit:**
- R² = 0.985  
- Adjusted R² = 0.982  
- F-statistic = 249.93 (p < 0.001)

**Significant variables:**
- **Income:** positive and significant (normal good)  
- **Price of chicken:** negative and significant (law of demand)  
- **Prices of beef and pork:** not statistically significant  

---

## Predictive Scenarios
Predicted chicken demand (in lbs) when:  
`income = 2400, pchick = 52, pbeef = 313, ppork = 171.5`

→ **Predicted consumption:** 65.66 lbs  

Interpretation:
- Increasing income by 1% raises demand by 0.34%.  
- Decreasing chicken price by 3% increases demand by approximately 1.5%.  

---

## Tools and Methods
- **Language:** R  
- **Key functions:** `lm()`, `predict()`, `linearHypothesis()`, `summary()`  
- **Packages:** `stats`, `car`, `carData`, `ggplot2`, `dplyr`  
- **Techniques:** Log-log regression, elasticity estimation, hypothesis testing, model diagnostics  

---

## Repository Structure
├── price-elasticity-estimation.Rmd   # R Markdown script  
├── chicken.csv   # Dataset  
├── docs/  
│   └── index.html   # Knitted report (viewable online)  
└── README.md  

---

## How to View
For an interactive and formatted report:
- View the rendered HTML file directly:  
  👉 [[https://nlinh03101-art.github.io/price-elasticity-estimation](https://nlinh03101-art.github.io/Price-Elasticity-Estimation/)/]

The `.Rmd` source file is provided for full reproducibility.

---

## Author
**Ngoc Linh Dao**  
*MSc in Management, Economics and Data Science*  
Focus: Applied analytics, econometrics, and data-driven decision optimization.  
🔗 [Main Portfolio](https://github.com/nlinh03101-art/Linh_portfolio)

---

## License
This repository is shared under the **MIT License**, allowing academic and educational reuse with attribution.
