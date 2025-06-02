# Risk Forecasting and Portfolio Tail Risk  
## Realized Volatility Modeling & Correlation-Based Strategy

This project explores univariate and bivariate financial risk modeling using high-frequency data. We replicate and evaluate various models for realized volatility forecasting, compute Value-at-Risk (VaR) and Expected Shortfall (ES), and design a simple trading strategy based on time-varying correlations between SPX and STOXX50.

### Part 1: Univariate Realized Volatility Forecasting
We model and forecast daily realized volatility using:

- **ARMA(1,1)** on log-realized variance (baseline short-memory benchmark)
- **HAR model** (Corsi, 2009) capturing long-memory behavior
- **HAR-RV-CJ model** incorporating downside risk and jump variation
- **Realized GARCH(1,1)** (Hansen et al., 2012) – both linear and log-linear versions

Each model is evaluated based on in-sample fit, out-of-sample forecasting accuracy (MSE, QLIKE), and its suitability for downstream risk estimation (VaR, ES).

### Part 2: Correlation-Based Trading Strategy
We estimate time-varying correlations using a **DCC-GARCH** framework and propose a regime-switching strategy:
- Stay long SPX and STOXX50
- Exit the market when correlation exceeds a high threshold
- Re-enter once correlation mean-reverts

We evaluate the strategy’s portfolio P&L, volatility reduction, Sharpe ratio, and tail risk (via Monte Carlo VaR/ES simulation).
