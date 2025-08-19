# Corn Morphological Analysis: Linear Regression Model for Plant Height Prediction

## Project Overview

This project develops a linear regression model to predict corn plant height using morphological characteristics. The analysis is based on three decades of data from the Portuguese Plant Germplasm Bank (BPGV), encompassing 566 regional corn populations with comprehensive morphological descriptors.

## Research Objective

The primary goal is to demonstrate the association between various morphological descriptors and establish a predictive model for plant height (ALP) in corn populations. This model serves practical applications in germplasm management, particularly for imputing missing data in historical collections.

## Dataset Description

The dataset contains morphological measurements from 566 corn populations collected over 30 years. Each record includes nine variables categorized into four descriptor types:

**Vegetative Descriptors:**
- ALP (Plant height in cm) - *Target variable*
- NTN (Total number of nodes)

**Foliar Descriptors:**
- NTF (Total number of leaves)
- ARF (Leaf area in cm²)

**Productive Descriptors:**
- CME (Ear length in cm)
- PMG (Thousand grain weight in g)

**Intrinsic Descriptors:**
- CDE (Endosperm color) - *Categorical: White, Cream, Light-yellow, Yellow, Orange*
- FAS (Fasciation) - *Binary: Present/Absent*

**Environmental Descriptor:**
- ALC (Harvest site altitude in m)

## Methodology

The analysis follows a systematic approach to model development and validation:

### Data Preparation
- Comprehensive exploratory data analysis including descriptive statistics
- Correlation analysis using Pearson correlation coefficients
- Assessment of variable relationships through ANOVA for categorical predictors

### Model Development
- Initial full model construction using all available predictors
- Multicollinearity assessment using Variance Inflation Factor (VIF)
- Variable selection through stepwise regression (forward, backward, and bidirectional)
- Model comparison using Akaike Information Criterion (AIC)

### Model Validation
- Residual normality testing using Shapiro-Wilk test
- Homoscedasticity verification through residual analysis
- Confidence interval computation for model parameters

## Key Findings

### Correlation Analysis
Strong positive correlations (>0.5) were identified between ear length (CME), number of leaves (NTF), leaf area (ARF), plant height (ALP), and number of nodes (NTN). A moderate negative correlation was observed between altitude (ALC) and other morphological variables.

### Model Performance
The final optimized model achieved:
- R-squared: 0.6689 (explaining 66.89% of variance in plant height)
- Residual Standard Error: 11% relative to mean plant height
- All model assumptions validated (normality, homoscedasticity, independence)

### Final Model Specification
**ALP ~ CME + NTF + PMG + CDE + NTN + FAS**

The stepwise selection process excluded only the altitude variable (ALC) from the original predictor set, with leaf area (ARF) removed earlier due to multicollinearity concerns.

## Statistical Significance

The model demonstrates robust statistical foundations with significant predictors at various confidence levels:
- Primary morphological descriptors (CME, NTF, PMG, NTN): p < 0.001
- Endosperm color levels (Yellow, Orange): p < 0.001  
- Fasciation presence: p < 0.05

## Practical Applications

This predictive model offers valuable applications for:
- Germplasm collection management and data quality improvement
- Missing data imputation in historical corn population records
- Morphological trait prediction for breeding program optimization
- Quality control in phenotypic characterization protocols

## Technical Implementation

### Requirements
- R statistical environment
- Required packages: readxl, summarytools, GGally, ggplot2, car, MASS, tidyverse, caret, leaps

### Usage
The complete analysis workflow is documented in the R Markdown file, providing reproducible results for similar datasets or extended analyses.

## Contributors

- Miguel Barros (pg42877)
- Tiago Machado (pg42884)  
- Tiago Silva (pg42885)

## Data Source

Portuguese Plant Germplasm Bank (BPGV) - Three decades of morphological characterization data from regional corn populations.

---

*This project demonstrates the practical application of statistical modeling in agricultural research, specifically showing how morphological descriptors can reliably predict plant characteristics in corn germplasm collections.*
