# Multi-Omics-Data-analysis-using-MOFA-in-R

# MOFA-Based Multi-Omics Analysis of AMP Genes and Clinical Outcomes

This repository contains a **Multi-Omics-Data-analysis-using-MOFA-in-R script** that performs a full analysis pipeline using MOFA, focused on AMP gene signatures and extended to include imputation and survival modeling.

---

##  What’s Included

- **Multi-Omics-Data-analysis-using-MOFA-in-R**: All code is in one file (` Multi-Omics-Data-analysis-using-MOFA-in-R.R`), with clear section headers to guide navigation.
- **AMP Gene Signature Analysis**: Integration of multi-omics data using MOFA with focus on AMP-related gene signatures.
- **Missing Data Imputation**: Model-based imputation using MOFA.
- **Clinical Outcome Modeling**: Survival analysis using Cox models and Kaplan-Meier plots based on MOFA factors.

---

##  File

- ` Multi-Omics-Data-analysis-using-MOFA-in-R.R`: Complete analysis script.

---

##  Workflow Overview

### 1. Load Data
- Load input multi-omics data: mRNA, DNA methylation, drug response, mutations.
- Load sample metadata and AMP gene list.

### 2. Prepare MOFA Object
- Format data into MOFA-compatible list structure.
- Create and configure MOFA object.
- Define model options and training parameters.

### 3. Train MOFA Model
- Train model on multiple omics views.
- Evaluate convergence and model performance.

### 4. Explore Results
- Plot variance explained per view and per factor.
- Visualize sample clustering and factor heatmaps.
- Investigate gene weights for AMP-related factors.

### 5. AMP Gene Analysis
- Subset and highlight AMP gene signatures across factors.
- Compare factor values between AMP and non-AMP samples.

---

## ➕ Additional Analyses

### A. Imputation of Missing Values
- Use `impute(MOFAobject)` to generate missing values.
- Access imputed matrices via `MOFAobject@imputed_data` or `get_imputed_data()`.

### B. Predictive Modeling of Clinical Outcome
- Use MOFA factors as predictors in a Cox proportional hazards model.
- Model time to treatment using survival data (`Surv()` function).
- Visualize hazard ratios and Kaplan-Meier curves.

---

## Requirements

Install the following R packages before running the script:

```r
install.packages(c("tidyverse", "survival", "survminer", "maxstat"))
# MOFA2 should be installed from Bioconductor or GitHub:
# BiocManager::install("MOFA2")
