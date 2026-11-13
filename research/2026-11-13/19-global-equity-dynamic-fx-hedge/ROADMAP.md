# ROADMAP — Dynamic Currency-Hedge and Rebalancing Tax for Global Equity
## Stage 0 — evidence feasibility (weeks 1–2)
- Validate public data meaning, historical vintages, publication lag and any commercial license for **US, Japan, euro area, UK and selected liquid EM equity markets**.
- Confirm action/market legal constraints, unit conventions and country equity market × FX forward tenor × monthly rebalance date.
- Gate: stop if input authorization, comparable baseline or event-time record is unavailable.

## Stage 1 — reproducible baseline (weeks 3–4)
- Create synthetic event fixtures with adverse missing/revision scenarios.
- Implement 50% static currency hedges plus equal-risk country weights and quarterly turnover. and hard feasibility tests.
- Gate: AC-001, AC-002, AC-005.

## Stage 2 — candidate science (weeks 5–8)
- Implement Robust covariance and transaction-cost-aware FX hedge optimizer., compare matched chronological holdouts, audit Country index histories have vendor survivorship and free-float methodological changes; FX pricing may be unavailable at allocated size..
- Consider Distributionally robust conditional hedge allocation with Markov stress regime and partial hedging. only on preregistered incremental value.
- Gate: Reject if lower-tail risk not improved by at least 5% net of forward carry and turnover without violating return floor.

## Stage 3 — controlled shadow evaluation (weeks 9–12)
- Measure after-cost drawdown, lower-tail CVaR, rolling correlation, FX hedge turnover and volatility., the relevant capacity constraints and all-in implementation cost.
- Replace illustrative 24-month ROI (-85% to 100%) with source-backed measured economics or explicitly retain uncertainty.
- Gate: independent risk/compliance review, adequate tail robustness, reproducibility evidence.

## Deferred production
Requires separate feature PR, CI, audit controls, monitoring, rollback and human authorization. No live trading or private data is authorized by this package.
