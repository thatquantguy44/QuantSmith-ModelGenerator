# ROADMAP — Weather Forecast Revision as an Electricity-to-Gas Risk Hedge
## Stage 0 — evidence feasibility (weeks 1–2)
- Validate public data meaning, historical vintages, publication lag and any commercial license for **US regional power markets and Henry Hub-linked energy**.
- Confirm action/market legal constraints, unit conventions and balancing authority × weather forecast issuance × lead hour.
- Gate: stop if input authorization, comparable baseline or event-time record is unavailable.

## Stage 1 — reproducible baseline (weeks 3–4)
- Create synthetic event fixtures with adverse missing/revision scenarios.
- Implement Seasonal degree-day demand regression and absolute temperature forecasts. and hard feasibility tests.
- Gate: AC-001, AC-002, AC-005.

## Stage 2 — candidate science (weeks 5–8)
- Implement Net-load forecast-revision elasticity with non-linear stress threshold., compare matched chronological holdouts, audit Archive of *historical forecasts as issued* may be inaccessible; today's historical observations are not contemporaneous forecasts..
- Consider Probabilistic shortfall-and-constraint model with weather ensemble calibration. only on preregistered incremental value.
- Gate: Reject if no improvements in forecast quantile loss or hedge after-cost variance over degrees-day baseline.

## Stage 3 — controlled shadow evaluation (weeks 9–12)
- Measure load p95 quantile loss, probabilistic calibration, hedge tracking error, net futures carry., the relevant capacity constraints and all-in implementation cost.
- Replace illustrative 24-month ROI (-100% to 176%) with source-backed measured economics or explicitly retain uncertainty.
- Gate: independent risk/compliance review, adequate tail robustness, reproducibility evidence.

## Deferred production
Requires separate feature PR, CI, audit controls, monitoring, rollback and human authorization. No live trading or private data is authorized by this package.
