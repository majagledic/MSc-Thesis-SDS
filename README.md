# MSc-Thesis-SDS
Code for Master's Thesis Statistics and Data Science: 
"Performance Evaluation of Interventional Prediction Models using Cross-validation"

## Counterfactual Performance Evaluation Using Different Nuisance Models
This repository contains the code and simulations for analyzing the impact of different nuisance model estimation strategies on counterfactual performance evaluation in a cross-validation setting. Treatment assignment was modeled using **Inverse Probability Weighting (IPW)**, and performance was evaluated using the **Brier score**.

-------------------
### Project Overview

This simulation-based project explores how different nuisance model estimation strategies influence counterfactual performance evaluation in a cross-validation setting. The focus is on the **estimation of the Brier score** under various sample sizes and model flexibility to assess **bias**, **variance**, and **RMSE** of the estimates.

The nuisance models, representing **propensity score models** used in IPW, were fit using four different estimation strategies:
1.  **Full data**
2.  **Training set only**
3.  **Test set only**
4.  **Separate nuisance set**

We examine how these strategies perform across varying:
- **Sample sizes**: 500, 1000, 1e4, and 1e5
- **Model complexities**:  
  - Logistic Regression (low flexibility)  
  - Generalized Additive Models (GAM)  
  - Random Forest  
  - Gradient Boosting (high flexibility)

Each combination of strategy, sample size, and model complexity was evaluated in a simulation study to assess:
- **Bias**: deviation from the true counterfactual Brier score
- **Variance**: across repetitions
- **RMSE**: overall error metric

The goal is to identify which estimation strategy yields the most accurate and reliable counterfactual performance estimates under various modeling conditions.

-----------------------
### Repository Structure

| File | Description |
|------|-------------|
| `Simulation_LR.Rmd` | **Logistic Regression** nuisance model |
| `Simulation_GAM.Rmd` | **Generalized Additive** nuisance model |
| `Simulation_RF.Rmd` | **Random Forest** nuisance model |
| `Simulation_GBM.Rmd` | **Gradient Boosting** nuisance model |

Each `.Rmd` file runs an independent simulation study, evaluates counterfactual Brier scores, and produces summary plots and tables.

---------------
### Requirements

- R (version ≥ 4.0.0 recommended)
- All necessary packages are loaded at the beginning of each `.Rmd` file

Commonly used packages include:
- `dplyr`, `ggplot2`, `tidyr`
- `mgcv`, `randomForest`, `gbm`, 
- `knitr`, `rmarkdown`

-------------------
### Running the Code

To run any of the simulation scripts:
  1. Open the desired `.Rmd` file in RStudio.
  2. Ensure all packages listed in the setup chunk are installed.
  3. Optional: Knit the file to produce HTML or PDF with embedded plots and tables.

 **Note:** The simulations are computationally intensive due to the large sample size
 (n = 100,000) and multiple repetitions (r = 100). Each file may take several hours to complete 
 depending on your system specifications.

---------
### Output

Each script produces:
- Plots showing the distribution of estimated Brier scores and average Brier scores from 100 simulation replication across varying samples
- Tables summarizing:
  - **Average Brier scores** across sample sizes
  - **Bias**, **variance**, and **RMSE** of the Brier score estimates

These outputs allow for comparison of model robustness and performance under varying data conditions.
