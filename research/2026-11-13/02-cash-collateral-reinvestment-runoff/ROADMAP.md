# ROADMAP — Cash-Collateral Reinvestment Liquidity Run-Off Controller
## Stage 0 — evidence feasibility (weeks 1–2)
- Validate public data meaning, historical vintages, publication lag and any commercial license for **US securities lending programs**.
- Confirm action/market legal constraints, unit conventions and cash collateral program × reinvestment maturity bucket × business day.
- Gate: stop if input authorization, comparable baseline or event-time record is unavailable.

## Stage 1 — reproducible baseline (weeks 3–4)
- Create synthetic event fixtures with adverse missing/revision scenarios.
- Implement Static liquidity buffer plus duration/weighted average life constraints. and hard feasibility tests.
- Gate: AC-001, AC-002, AC-005.

## Stage 2 — candidate science (weeks 5–8)
- Implement Conditional run-off survival model combined with stochastic cash-flow gap optimizer., compare matched chronological holdouts, audit Return flows may cluster under crises; survivorship of reinvestment balances causes understated withdrawals..
- Consider Distributionally robust multi-period policy with borrower return clustering and fire-sale haircuts. only on preregistered incremental value.
- Gate: Reject if stress shortfalls are not reduced by at least 10% without degrading contractual yield or creating maturity breaches.

## Stage 3 — controlled shadow evaluation (weeks 9–12)
- Measure 99% liquidity shortfall, reinvestment net yield, liquidity carry, stressed liquidations, breach count., the relevant capacity constraints and all-in implementation cost.
- Replace illustrative 24-month ROI (-58% to 105%) with source-backed measured economics or explicitly retain uncertainty.
- Gate: independent risk/compliance review, adequate tail robustness, reproducibility evidence.

## Deferred production
Requires separate feature PR, CI, audit controls, monitoring, rollback and human authorization. No live trading or private data is authorized by this package.
