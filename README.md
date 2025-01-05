# Colon Cancer Treatment Analysis Technical Report

## Overview
This repository contains a technical analysis of stage III colon cancer treatment outcomes, analyzing the effectiveness of different adjuvant therapy approaches. The study compares three treatment groups: observation only (control), levamisole alone, and fluorouracil plus levamisole combination therapy. The purpose for this analysis is to select a best model for colon dataset.

## Dataset
The analysis utilizes the 'colon' dataset from the R survival package, which includes:
- 16 variables
- Stage III colon cancer patients
- Treatment randomization into three arms
- Death events (etype = 2)
- Lymph node status
- Various clinical and demographic variables

## Methods
The analysis employed multiple statistical approaches:
1. Kaplan-Meier survival analysis with log-rank tests
2. Three Cox proportional hazards models:
   - Unadjusted model
   - Adjusted model with confounders
   - LASSO penalized regression model
3. Model comparison using:
   - AIC/BIC criteria
   - Harrell's C-index for discrimination
   - Calibration metrics

## Key Findings
- Combination therapy (Lev+5FU) showed a 29% reduction in mortality risk (HR=0.71, 95% CI: 0.56-0.90)
- Levamisole alone had minimal effect (HR = 0.95, 95% CI: 0.76-1.18, p = 0.628)
- Strong prognostic factors identified:
  - Number of positive lymph nodes (≥4 nodes increased risk by 93%)
  - Extent of tumor spread (contiguous spread increased risk 4.2-fold)
  - Obstruction status

## Model Selection
The Full model (adjusted Cox with stratification) was selected as optimal due to:
- Lowest AIC (4307.85) and BIC (4356.62)
- Highest C-index (0.683)
- 31.5% improvement in discrimination vs. unadjusted model
- Significant improvement over both LASSO and unadjusted models

## Code and Reproducibility
- Analysis conducted using R
- Code available in 'colon' file
- Includes all numerical results and plots
- Full statistical methodology documented in technical report

## Comparison with Original Research
Findings align with original paper's conclusions:
- Similar treatment effect sizes
- Consistent prognostic factors
- Main difference in statistical methodology (modern approaches used)

## Files
- Quick View: Statistical Analysis Plan for Replication
- Original paper: moertel-et-al-2000-fluorouracil-plus-levamisole-as-effective-adjuvant-therapy-after-resection-of-stage-iii-colon.pdf
- Technical Report (PDF)
- R code: colon.Rmd

## Dependencies
- R statistical software
- survival package
- glmnet package (for LASSO)
- ggplot2 (for visualization)
