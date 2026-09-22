# Estimation Risk in Mean Variance Portfolios

How much of a mean variance portfolio is signal, and how much is estimation error? This notebook answers that on the 11 SPDR sector ETFs from June 2018 to September 2026, with SPY as the market factor and a passive benchmark.

## What's inside

1. A cached, reproducible data pipeline for adjusted daily prices
2. Simulation, bootstrap and rolling window studies of how badly μ and Σ are estimated
3. Sensitivity of optimal weights to γ, μ, correlations and volatility
4. A static backtest with rebalancing frequency and transaction costs
5. A walk forward backtest with a rolling three year window, monthly rebalancing, costs and fees
6. Minimum variance and risk parity as benchmarks that ignore μ

## Headline result

Constrained mean variance returned a Sharpe of 0.557 out of sample over 5.2 years. Equal weight returned 0.766 and SPY returned 0.812. Risk parity, which estimates almost nothing, beat mean variance on every metric. The estimates subtracted value.

## How to run

```
pip install -r requirements.txt
jupyter notebook mean_variance_estimation_risk.ipynb
```

Restart the kernel and Run All. The price panel ships in `data/prices.csv` and is frozen at September 4, 2026, so every number in the notebook reproduces exactly with no network call.
