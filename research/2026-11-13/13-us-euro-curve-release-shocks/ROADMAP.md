# ROADMAP — US–Euro Sovereign Curve Shock Decomposition with Data Vintages
## Stage 0 — evidence feasibility (weeks 1–2)
- Validate public data meaning, historical vintages, publication lag and any commercial license for **United States and euro area**.
- Confirm action/market legal constraints, unit conventions and economic release event × curve tenor × publication instant × geography.
- Gate: stop if input authorization, comparable baseline or event-time record is unavailable.

## Stage 1 — reproducible baseline (weeks 3–4)
- Create synthetic event fixtures with adverse missing/revision scenarios.
- Implement 60-day rolling DV01-neutral cross-market beta hedge. and hard feasibility tests.
- Gate: AC-001, AC-002, AC-005.

## Stage 2 — candidate science (weeks 5–8)
- Implement Vintaged announcement factor model plus shrinkage hedge weights., compare matched chronological holdouts, audit Public releases cannot recreate market consensus surprises without a licensed historical consensus dataset or explicit no-consensus baseline..
- Consider Hierarchical structural yield-curve state-space with distinct real-rate and term-premium factor loading. only on preregistered incremental value.
- Gate: Reject if hedge variance does not improve at least 5% net of turnover on independent event holdout.

## Stage 3 — controlled shadow evaluation (weeks 9–12)
- Measure OOS hedging variance reduction, implementation shortfall, tail DV01 loss, signal turnover., the relevant capacity constraints and all-in implementation cost.
- Replace illustrative 24-month ROI (-100% to 115%) with source-backed measured economics or explicitly retain uncertainty.
- Gate: independent risk/compliance review, adequate tail robustness, reproducibility evidence.

## Deferred production
Requires separate feature PR, CI, audit controls, monitoring, rollback and human authorization. No live trading or private data is authorized by this package.
