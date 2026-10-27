# Bitcoin, Ethereum, Gold and VIX: Bayesian Regression and Model Selection

**Group project** – Bayesian Computing Methods, University of Perugia (Feb–Jun 2026)

## Question

What drives Bitcoin returns? Monthly Bitcoin log-returns (2016–2024) are explained using Ethereum, gold (GLD) and the VIX.

## 1. Bayesian linear regression (`01_bayesian_linear_regression.qmd`)

- Bayesian multiple regression with **conjugate Normal–Inverse-Gamma priors**, implemented from scratch
- Closed-form posterior, validated with **3,000 Monte Carlo draws**
- Comparison with OLS: the apparent effect of gold (0.26) shrinks to **0.04**, showing it was weakly supported by the data
- Ethereum is the strongest predictor: a 1% increase in ETH returns is associated with a ~0.39% increase in BTC returns

## 2. Model selection (`02_model_selection.qmd`)

- All **8 possible models** (2³ combinations of predictors) compared with **AIC, BIC and Bayes Factors**
- **Ethereum alone (M1)** is the best model under every criterion
- Evidence for M1 against the null model is **decisive** (BF ≈ 6 × 10¹¹); adding gold and the VIX does not justify the extra complexity

## How to run

The `.qmd` files are Quarto documents (R). They expect a semicolon-separated file `DATITESI.csv` with monthly prices `P_BTC`, `P_ETH`, `P_GLD`, `P_VIX` (source: Investing.com), which is not included in this repository.

## Tools

R · Quarto · mvtnorm · car
