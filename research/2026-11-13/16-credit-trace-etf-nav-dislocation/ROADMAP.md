# ROADMAP — Corporate-Bond TRACE Liquidity-to-ETF NAV Stress Transmission
## Stage 0 — evidence feasibility (weeks 1–2)
- Validate public data meaning, historical vintages, publication lag and any commercial license for **United States investment-grade/high-yield credit; optional Europe comparison**.
- Confirm action/market legal constraints, unit conventions and bond × disseminated trade timestamp × ETF NAV publication timestamp.
- Gate: stop if input authorization, comparable baseline or event-time record is unavailable.

## Stage 1 — reproducible baseline (weeks 3–4)
- Create synthetic event fixtures with adverse missing/revision scenarios.
- Implement ETF realized volatility and quoted bid-ask spread. and hard feasibility tests.
- Gate: AC-001, AC-002, AC-005.

## Stage 2 — candidate science (weeks 5–8)
- Implement Robust bond-liquidity dispersion index and ETF tracking-state model., compare matched chronological holdouts, audit Reported bond prices may be size-capped/delayed; TRACE trade access/licensing varies and NAV can embed stale marks..
- Consider Structural ETF redemption/creation network with dealer intermediation bottlenecks. only on preregistered incremental value.
- Gate: Reject if no incremental tracking error forecast or lower stress drawdown after NAV timestamp normalization and realistic ETF costs.

## Stage 3 — controlled shadow evaluation (weeks 9–12)
- Measure tracking error forecast, credit tail loss, hedge slippage, redemption-state calibration., the relevant capacity constraints and all-in implementation cost.
- Replace illustrative 24-month ROI (-100% to 112%) with source-backed measured economics or explicitly retain uncertainty.
- Gate: independent risk/compliance review, adequate tail robustness, reproducibility evidence.

## Deferred production
Requires separate feature PR, CI, audit controls, monitoring, rollback and human authorization. No live trading or private data is authorized by this package.
