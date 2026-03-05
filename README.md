# Efficient Frontier Portfolio Optimization

This project implements **portfolio optimization using Modern Portfolio Theory (MPT)** in Python.  
It calculates the **optimal asset allocation that maximizes the Sharpe Ratio**, constructs the **Efficient Frontier**, and performs **Monte Carlo simulations to estimate portfolio risk (VaR and CVaR).**

The project uses historical stock data from **Yahoo Finance**.

---

## Features

- Fetch historical stock data using `yfinance`
- Calculate **expected returns and covariance matrix**
- Optimize portfolio weights using **Sharpe Ratio maximization**
- Plot the **Efficient Frontier**
- Perform **Monte Carlo simulations** to model future portfolio performance
- Calculate risk metrics:
  - **Value at Risk (VaR)**
  - **Conditional Value at Risk (CVaR)**

---

## Technologies Used

- Python
- pandas
- numpy
- matplotlib
- scipy
- yfinance

---

## Stocks Used

The portfolio contains the following Indian stocks:

- RELIANCE
- TCS
- HDFCBANK
- ICICIBANK
- INFY
- ITC

Data is fetched from **Yahoo Finance** using ticker symbols with `.NS`.

---

## Methodology

### 1. Data Collection
Historical stock prices are downloaded using the `yfinance` API.

### 2. Return Calculation
Daily returns are calculated and used to estimate:

- Mean returns
- Covariance matrix

### 3. Portfolio Optimization
The optimal portfolio is obtained by **maximizing the Sharpe Ratio** using `scipy.optimize`.

Constraints used:
- Sum of weights = 1
- No short selling (weights between 0 and 1)

### 4. Efficient Frontier
The Efficient Frontier is constructed by minimizing volatility for a range of target returns.

This shows the **risk-return tradeoff for optimal portfolios**.

### 5. Monte Carlo Simulation
A **Monte Carlo simulation with 1000 simulations and 252 trading days** is used to estimate potential portfolio outcomes.

Cholesky decomposition is used to generate **correlated asset returns**.

### 6. Risk Metrics

From the simulation results we compute:

**Value at Risk (VaR)**  
Maximum expected loss at a given confidence level.

**Conditional Value at Risk (CVaR)**  
Expected loss given that the VaR threshold is exceeded.

---

## Results

The project outputs:

- Optimal portfolio weights
- Efficient Frontier plot
- Monte Carlo simulation distribution
- 95% Value at Risk (VaR)
- 95% Conditional Value at Risk (CVaR)

---

## Example Visualizations

### Efficient Frontier
Shows optimal risk-return combinations.

<img width="857" height="547" alt="efficient_frontier" src="https://github.com/user-attachments/assets/a4fe2e0f-bef1-4a09-a5ad-2b5edb37a001" />

### Monte Carlo Simulation
Distribution of possible end-of-year portfolio values.

<img width="841" height="547" alt="monte_carlo" src="https://github.com/user-attachments/assets/2fe30b4a-798f-4c31-a344-2e08c9685f97" />

---

## Installation

Clone the repository:

```bash
git clone https://github.com/ThusSpokeSwan/efficient-frontier-portfolio-optimization.git
```

Install dependencies:

```bash
pip install pandas numpy matplotlib scipy yfinance
```

Run the notebook or Python script:

```bash
python portfolio_optimization.py
```
