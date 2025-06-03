# Risk Forecasting and Portfolio Tail Risk  
## Realized Volatility Modeling & Correlation-Based Strategy

This project explores univariate and bivariate financial risk modeling using high-frequency data. It replicates and evaluates various models for realized volatility forecasting, computes Value-at-Risk (VaR) and Expected Shortfall (ES), and designs a simple trading strategy based on time-varying correlations between SPX and STOXX50.

### Part 1: Univariate Realized Volatility Forecasting
Daily realized volatility is modeled using:

- **ARMA(1,1)** on log-realized variance (baseline short-memory benchmark)
- **HAR model** (Corsi, 2009) capturing long-memory behavior
- **HAR-RV-CJ model** incorporating downside risk and jump variation
- **Realized GARCH(1,1)** (Hansen et al., 2012) – both linear and log-linear versions

Each model is evaluated based on in-sample fit, out-of-sample forecasting accuracy (MSE, QLIKE), and its suitability for downstream risk estimation (VaR, ES).

### Part 2: Correlation-Based Trading Strategy
Time-varying correlations are estimated using a **DCC-GARCH** framework and a regime-switching strategy is proposed:
- Stay long SPX and STOXX50
- Exit the market when correlation exceeds a high threshold
- Re-enter once correlation mean-reverts

The strategy’s portfolio P&L, volatility reduction, Sharpe ratio, and tail risk (via Monte Carlo VaR/ES simulation) are then evaluated.

**Note**  
The dataset used in this project is not included in the repository due to licensing restrictions. You can replicate the results by applying the models to your own high-frequency intraday data or similar datasets.
