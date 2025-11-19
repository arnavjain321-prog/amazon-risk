# Modeling S&P 500 Stock Dynamics Using Non-Parametric Methods  
### Case Study: Amazon (AMZN)

## Overview
This project analyzes the daily return distribution and volatility characteristics of Amazon (AMZN) using non-parametric statistical methods. Non-parametric techniques allow us to model return behavior directly from the data without assuming a specific distributional form. The analysis focuses on understanding heavy tails, volatility clustering, and risk estimation through bootstrapping.

The project includes:
- Data cleaning and selection of AMZN from a larger S&P 500 dataset
- Calculation of log returns
- Kernel Density Estimation (KDE)
- Comparison with a normal distribution benchmark
- Bootstrapping of returns to simulate risk scenarios
- Estimation of Value at Risk (VaR) and Expected Shortfall (ES)

## Data Description
The original dataset contains historical prices for all S&P 500 companies. Many companies have incomplete histories due to listing and delisting events, stock splits, corporate actions, and changes in index membership. To maintain a consistent time series, the analysis focuses on Amazon (AMZN), which provides complete historical price data.

The dataset used in this project:
- File: data/sp500_stocks.csv
- Columns include: Date, Symbol, Open, High, Low, Close, Volume

## Methods and Analysis

### 1. Data Cleaning
Filtered to AMZN, sorted by date, handled missing values, and computed daily log returns: r_t = ln(P_t / P_(t-1)).

### 2. Exploratory Data Analysis
Examined time series behavior, return distribution shape, and differences from a normal distribution.

### 3. Kernel Density Estimation (KDE)
Applied KDE to estimate the empirical return density. This highlights skewness, fat tails, and deviations from Gaussian assumptions.

### 4. Bootstrapping
Resampled returns with replacement to generate synthetic return paths. This allows estimating uncertainty, extreme events, and confidence intervals for risk metrics.

### 5. Risk Metrics
Value at Risk (VaR): return threshold not exceeded with a given confidence level.  
Expected Shortfall (ES): the average loss conditional on returns exceeding the VaR threshold.

## Repository Structure

project root/  
    amazon-risk.ipynb            Main Jupyter notebook containing the analysis  
    README.md                 Project documentation  
    .gitignore                Git ignore file  
    data/  
        sp500_stocks.csv      Source dataset  

## How to Run
1. Clone the repository: git clone https://github.com/arnavjain321-prog/amazon-risk.git
2. Install dependencies: numpy, pandas, matplotlib, seaborn, scipy, scikit-learn, statsmodels
3. Open the notebook: jupyter notebook project1.ipynb

## Summary of Findings
- Amazon returns exhibit heavy tails relative to the normal distribution.
- Volatility is clustered, with alternating calm and turbulent periods.
- KDE captures the empirical distribution more accurately than Gaussian assumptions.
- Bootstrapping reveals uncertainty in tail behavior and produces robust VaR and ES estimates.
- Non-parametric modeling provides a flexible, data-driven understanding of return characteristics without restrictive assumptions.

## Notes
This project was completed for DS 5030 (Project 1). All analysis was conducted in Python using open-source libraries.
