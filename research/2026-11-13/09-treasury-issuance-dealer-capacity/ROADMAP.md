# ROADMAP — Treasury Issuance-to-Dealer Intermediation Capacity Map
## Stage 0 — evidence feasibility (weeks 1–2)
- Validate public data meaning, historical vintages, publication lag and any commercial license for **United States issuance and dealer system**.
- Confirm action/market legal constraints, unit conventions and issuance cohort × week of publicly released dealer aggregates.
- Gate: stop if input authorization, comparable baseline or event-time record is unavailable.

## Stage 1 — reproducible baseline (weeks 3–4)
- Create synthetic event fixtures with adverse missing/revision scenarios.
- Implement Treasury yield volatility and calendar week indicators. and hard feasibility tests.
- Gate: AC-001, AC-002, AC-005.

## Stage 2 — candidate science (weeks 5–8)
- Implement Event-study + state-space dealer supply absorption proxy., compare matched chronological holdouts, audit Aggregate dealer reports cannot identify securities or dealers and issuance is endogenous to financing conditions..
- Consider Instrumented quasi-experiment using prescheduled auction supply shocks and cross-CUSIP constraints. only on preregistered incremental value.
- Gate: Reject if no improvement over the rate-volatility-only benchmark on genuinely held-out issuance regimes.

## Stage 3 — controlled shadow evaluation (weeks 9–12)
- Measure stress forecast Brier, AUPRC, lead-time, false positives and hedge drawdown., the relevant capacity constraints and all-in implementation cost.
- Replace illustrative 24-month ROI (-75% to 70%) with source-backed measured economics or explicitly retain uncertainty.
- Gate: independent risk/compliance review, adequate tail robustness, reproducibility evidence.

## Deferred production
Requires separate feature PR, CI, audit controls, monitoring, rollback and human authorization. No live trading or private data is authorized by this package.
