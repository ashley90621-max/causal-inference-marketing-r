# Causal Inference in Marketing

**Course**: MSIN0094 Marketing Analytics | UCL School of Management  
**Author**: Kuei-Chun Liu  
**Tools**: R · Quarto · dplyr · fixest · ggplot2 · rdrobust

---

## Overview

This project applies causal inference methods to real-world marketing problems using TV retail data. Moving beyond correlation, it identifies the true causal effects of pricing, branding, and marketing spend on sales.

## Contents

| File | Description |
|---|---|
| `assignment3_answer_sheet.qmd` | Full analysis in Quarto Markdown |
| `data_full.csv` | Weekly TV retail panel data (multi-brand) |

## Key Analyses

**1. Descriptive Analytics**  
Price-sales scatter plot and brand revenue ranking using dplyr. Samsung ranked highest in average weekly dollar sales.

**2. Marketing Mix Modeling (OLS)**  
Linear regression of sales on price and marketing spend. Identified endogeneity issues: omitted variable bias, simultaneity, and measurement error.

**3. Fixed Effects Regression**  
Used `fixest::feols` with brand and week fixed effects to control for unobserved confounders and recover causal price elasticity.

**4. A/B Test Design (Amazon VTO)**  
Designed a randomised experiment (80/10/10 split) to test Virtual Try-On feature impact on spending and conversion. Analysed with OLS and logistic regression.

**5. Regression Discontinuity Design (RDD)**  
Used top-20% marketing spend threshold as a natural experiment cutoff. Found a causal lift of ~172 units in sales above the threshold (p < 0.001).

## How to Run

1. Open `assignment3_answer_sheet.qmd` in RStudio
2. Ensure `data_full.csv` is in the same directory
3. Install required packages:
```r
pacman::p_load(dplyr, fixest, modelsummary, ggplot2, rdrobust, broom)
```
4. Click **Render** to generate the HTML report
