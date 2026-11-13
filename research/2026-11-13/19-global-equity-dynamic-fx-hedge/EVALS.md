# EVALS — Dynamic Currency-Hedge and Rebalancing Tax for Global Equity
**Status:** Design for tests, no experiment performed.

## Economic claim and comparator
- **H1:** State-adaptive hedging reduces after-cost drawdown without sacrificing a pre-specified return floor relative to 0%, 50% and 100% static hedges.
- **Comparator:** 50% static currency hedges plus equal-risk country weights and quarterly turnover..
- **Candidate:** Robust covariance and transaction-cost-aware FX hedge optimizer..
- **Advanced alternative:** Distributionally robust conditional hedge allocation with Markov stress regime and partial hedging..
- **Metrics:** after-cost drawdown, lower-tail CVaR, rolling correlation, FX hedge turnover and volatility..
- **Stop/no-go:** Reject if lower-tail risk not improved by at least 5% net of forward carry and turnover without violating return floor.
- **Cost sensitivity:** USD $135k hypothetical 24-month engineering/data/maintenance cost; gross benefit sensitivity $20k–$270k over 24 months. Net ROI = (gross benefit − cost)/cost = **-85% to 100%**. NOT forecast or historical measurement. Economic lever: hypothetical $30m equity exposure; 0–42 bps annually saved from hedge inefficiency and drawdown control; weak scenario still pays some operational value.

## Evaluation splits and safeguards
1. Set chronologically non-overlapping training, validation and holdout periods; embargo trades with outcome windows crossing splits.
2. Align all records to first permitted information availability, not economic reference date. rebalance at scheduled month-end using prior-close prices and then-available forward quotes
3. Use exactly matched feasible opportunity sets and complete funding, execution, regulatory and operational frictions for baseline/candidate.
4. Compare against **no-action** when the cost of the position or data is not measurable.
5. Use time-blocked paired bootstrap uncertainty, relevant alternative market regimes and explicit multiple-hypothesis correction.
6. Test adverse implementation constraints: Limit to index futures/ETFs and deliverable/non-deliverable forward liquidity; enforce market access and capital controls.
7. Stress identification risk: Country index histories have vendor survivorship and free-float methodological changes; FX pricing may be unavailable at allocated size.
8. Record both gross and net metrics; a statistically significant signal is not necessarily profitable or operationally feasible.

## Specific negative/invariant tests
non-deliverable forward restrictions; hedge roll at bid/ask; timezone close mismatch; dynamic survivorship.

## Shadow mode and production gate
AC-001–AC-005 need test evidence and reproducible run envelopes. No trading or execution without human risk and legal approval; where public proxies are insufficient, block P&L claims and publish only a risk-monitoring exploratory result. The accepted outcome may be **negative** and should remain in the research archive.
