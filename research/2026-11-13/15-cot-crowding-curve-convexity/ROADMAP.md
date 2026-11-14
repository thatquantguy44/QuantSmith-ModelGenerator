# ROADMAP — CFTC Positioning Concentration and Commodity Curve Convexity
## Stage 0 — evidence feasibility (weeks 1–2)
- Validate public data meaning, historical vintages, publication lag and any commercial license for **United States commodity futures with global supply chains**.
- Confirm action/market legal constraints, unit conventions and CFTC contract market × Tuesday reference position × Friday public release, then weekly trade clock.
- Gate: stop if input authorization, comparable baseline or event-time record is unavailable.

## Stage 1 — reproducible baseline (weeks 3–4)
- Create synthetic event fixtures with adverse missing/revision scenarios.
- Implement Futures curve carry/roll-yield and 12-month time-series momentum. and hard feasibility tests.
- Gate: AC-001, AC-002, AC-005.

## Stage 2 — candidate science (weeks 5–8)
- Implement Positioning-conditioned conditional expected shortfall regression., compare matched chronological holdouts, audit CFTC taxonomy changes, combined report double-counting and slow publication may annihilate predictive edge..
- Consider Stochastic inventory-demand equilibrium with nonlinear dealer hedging and curve impact. only on preregistered incremental value.
- Gate: Reject if tail-risk control does not beat carry/momentum or negative convexity effect changes sign in out-of-sample contracts.

## Stage 3 — controlled shadow evaluation (weeks 9–12)
- Measure tail loss reduction, annualized Sharpe after roll/slippage, opportunity-cost drag and hedge stability., the relevant capacity constraints and all-in implementation cost.
- Replace illustrative 24-month ROI (-100% to 138%) with source-backed measured economics or explicitly retain uncertainty.
- Gate: independent risk/compliance review, adequate tail robustness, reproducibility evidence.

## Deferred production
Requires separate feature PR, CI, audit controls, monitoring, rollback and human authorization. No live trading or private data is authorized by this package.
