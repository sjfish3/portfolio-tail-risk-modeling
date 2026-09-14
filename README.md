# Portfolio Tail-Risk Modeling

This project compares several approaches to estimating and backtesting portfolio tail risk, with a focus on how distributional assumptions and time-varying volatility affect Value at Risk (VaR) and Expected Shortfall (ES).

The analysis uses an equally weighted multi-asset portfolio containing SPY, QQQ, IWM, TLT, and GLD. Models are evaluated using out-of-sample forecasts and formal VaR coverage tests.

## Research Question

How do distributional assumptions and time-varying volatility affect portfolio tail-risk estimation and out-of-sample VaR performance?

## Methods

The project compares four primary approaches:

- Normal parametric VaR
- Student-t parametric VaR
- Historical Simulation
- GARCH(1,1) with Student-t innovations

The analysis includes:

- exploratory return-distribution analysis
- volatility and correlation analysis
- VaR and Expected Shortfall estimation
- GARCH model selection using information criteria
- expanding-window out-of-sample backtesting
- VaR breach-rate analysis
- Kupiec unconditional coverage tests
- Christoffersen independence tests
- conditional coverage tests
- portfolio volatility contribution analysis

## Key Findings

Portfolio returns exhibited heavy tails and slight negative skew, although skewed model specifications did not improve model selection criteria enough to justify the additional complexity.

The Normal and static Student-t models showed an interesting calibration trade-off. The Normal model performed reasonably at the 95% confidence level but underestimated more extreme 99% tail losses. The Student-t model provided stronger protection in the extreme tail but was too conservative at the 95% level.

Historical Simulation and GARCH-t produced the most consistent overall backtesting results. Historical Simulation benefited from preserving the empirical return distribution, while GARCH-t combined heavy-tailed innovations with time-varying volatility and provided the strongest overall balance of flexibility and calibration.

The portfolio was equally weighted by capital, but risk contributions were highly unequal. SPY, QQQ, and IWM accounted for roughly 88% of total portfolio volatility, showing that equal capital allocation does not imply equal risk allocation.

## Data

Market price data for SPY, QQQ, IWM, TLT, and GLD are downloaded directly through yfinance, so no separate data files are required to reproduce the analysis.

## Repository Structure

```text
.
├── portfolio_risk_modeling.ipynb
├── README.md
└── requirements.txt