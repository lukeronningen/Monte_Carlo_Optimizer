# Monte Carlo Portfolio Optimizer

A Python-based portfolio optimization tool that uses **Monte Carlo simulation** and **Modern Portfolio Theory** to find the weight allocation that maximizes risk-adjusted return across a 10-stock portfolio.

## Overview

This project constructs a diversified portfolio of 10 publicly traded stocks, simulates thousands of random weight combinations, and identifies the portfolio with the highest **Sharpe ratio**. It also plots the **efficient frontier** to visualize the optimal risk-return tradeoff.

## How It Works

1. **Data Collection** — Downloads 5 years of daily adjusted close prices (2021–2026) using `yfinance`
2. **Return Analysis** — Calculates daily returns, annualizes them, and builds a covariance matrix
3. **Stock Analysis** — Generates cumulative return plots and a correlation heatmap to evaluate diversification
4. **Monte Carlo Simulation** — Runs 1,000 random portfolio simulations, computing return, volatility, and Sharpe ratio for each
5. **Optimization** — Identifies the maximum Sharpe ratio portfolio and reports optimal weight allocations
6. **Efficient Frontier** — Uses `scipy.optimize.minimize` (SLSQP) to trace the efficient frontier curve

## Portfolio

| Ticker | Company |
|--------|---------|
| AAPL | Apple |
| MCD | McDonald's |
| JPM | JPMorgan Chase |
| AMZN | Amazon |
| JNJ | Johnson & Johnson |
| TSLA | Tesla |
| NVDA | NVIDIA |
| AVGO | Broadcom |
| KO | Coca-Cola |
| WMT | Walmart |

## Key Assumptions

- **Data window:** 2021-01-01 to 2026-01-01
- **Risk-free rate:** 3%
- **Annualization:** 252 trading days
- **Constraints:** Long-only (all weights ≥ 0, sum to 1)

## Technologies

- Python · Pandas · NumPy · Matplotlib · Seaborn · yfinance · SciPy

## Sample Output

The optimizer produces:
- **Optimal weight allocation table** for maximum Sharpe ratio
- **Efficient frontier plot** with all simulated portfolios color-coded by Sharpe ratio
- **Cumulative return chart** and **correlation heatmap** for individual stock analysis

## Usage

```bash
# Clone the repo
git clone https://github.com/lukeronningen/Monte_Carlo_Optimizer.git

# Install dependencies
pip install pandas numpy matplotlib seaborn yfinance scipy

# Open the notebook
jupyter notebook Monte_Carlo_Optimizer.ipynb
```

## Author

**Luke Ronningen** — Built as a portfolio optimization project applying Modern Portfolio Theory and quantitative finance concepts in Python.
