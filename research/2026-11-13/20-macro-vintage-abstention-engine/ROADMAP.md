# ROADMAP — Macro-Vintage Integrity Engine with Prediction Abstention
## Stage 0 — evidence feasibility (weeks 1–2)
- Validate public data meaning, historical vintages, publication lag and any commercial license for **United States, euro area and OECD countries**.
- Confirm action/market legal constraints, unit conventions and economic indicator × observation period × release date × vintage ID.
- Gate: stop if input authorization, comparable baseline or event-time record is unavailable.

## Stage 1 — reproducible baseline (weeks 3–4)
- Create synthetic event fixtures with adverse missing/revision scenarios.
- Implement Always-on macro momentum score built from latest-vintage series. and hard feasibility tests.
- Gate: AC-001, AC-002, AC-005.

## Stage 2 — candidate science (weeks 5–8)
- Implement As-of macro feature store with release-confidence model and abstention., compare matched chronological holdouts, audit ALFRED historical series coverage, future revisions and OECD methodological breaks can be incomplete; abstention selection bias..
- Consider Bayesian missing-data multiple-vintage filtering and conformal selective prediction with capacity-aware portfolio overlay. only on preregistered incremental value.
- Gate: Reject if abstention fails to reduce loss on corrected vintage history or simply abstains from all market decisions.

## Stage 3 — controlled shadow evaluation (weeks 9–12)
- Measure revision-induced backtest bias, selective risk loss, coverage, false alarm rate, time-to-data-availability., the relevant capacity constraints and all-in implementation cost.
- Replace illustrative 24-month ROI (-85% to 88%) with source-backed measured economics or explicitly retain uncertainty.
- Gate: independent risk/compliance review, adequate tail robustness, reproducibility evidence.

## Deferred production
Requires separate feature PR, CI, audit controls, monitoring, rollback and human authorization. No live trading or private data is authorized by this package.
