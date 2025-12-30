# Probability of Default Modelling

Probability of default (PD) is one of the core components of Expected Loss (EL), used to measure the likelihood that a borrower will default on a loan. This project uses simulated credit bureau data to develop and evaluate a PD model.  

## Project Overview

This project takes on an learning-focused and explanatory approach to PD modelling; exploring modelling principles and methods, including:
- Handling missing data through flagging & imputation
- Categorical feature encoding using Weight of Evidence (WoE)
- Investigation of potential label leakage: comparing models trained with and without a leaky feature
- Model evaluation using AUC-ROC, Brier Score, Brier Skill Score (BSS), and calibration curves 

## Dataset 

- **Source:** [Credit Risk Dataset (Kaggle)](https://www.kaggle.com/datasets/laotse/credit-risk-dataset/data)
- **Description:** Simulated consumer credit bureau data
- **Size:** ~35,000 observations

## How To Run

**Requirements:**
- Python 3.x
- Libraries: `pandas`, `matplotlib`, `sklearn`, `feature-engine`
- Any Jupyter notebook environment 

**Steps:**
1. Clone this repository
```
```

2. Optional: Install dependencies
```
pip install -r requirements.txt
```

3. Open the notebook (`pd_modelling.ipynb`) and run all cells.

## Key Findings
- The final PD model achieved: 
    - **Brier Score:** 0.112
    - **AUC-ROC:** 0.852
    - **Brier Skill Score (BSS):** 0.339
- Corresponds to ~34% reduction in squared probability error relative to the baseline (BSref) model.
- A comparison between models trained with and without the interest rate feature showed:
    - The model trained *without* interest rate data slightly improved both calibration and error rate.
    - This suggests that interest rate may reflect pricing decisions rather than independent risk information, and may overlap with other risk related features, such as loan grade.

<p align='center'>
    <img src = 'figures/compared_curve.png' alt='Calibration curve comparison'>
</p>
