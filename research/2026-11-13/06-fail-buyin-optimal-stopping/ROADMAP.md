# ROADMAP — Settlement-Fail Buy-In versus Wait Optimal Stopping
## Stage 0 — evidence feasibility (weeks 1–2)
- Validate public data meaning, historical vintages, publication lag and any commercial license for **US Treasury and agency settlement**.
- Confirm action/market legal constraints, unit conventions and failed settlement instruction × elapsed failed day × cut-off timestamp.
- Gate: stop if input authorization, comparable baseline or event-time record is unavailable.

## Stage 1 — reproducible baseline (weeks 3–4)
- Create synthetic event fixtures with adverse missing/revision scenarios.
- Implement Auto-escalate after fixed N-day failure age. and hard feasibility tests.
- Gate: AC-001, AC-002, AC-005.

## Stage 2 — candidate science (weeks 5–8)
- Implement Discrete-time survival model with exact dynamic-programming stopping rule., compare matched chronological holdouts, audit Fails charges and rights to enforce buy-ins differ by asset, market and contract; wrong assumptions invalidate decisions..
- Consider Partial-observation optimal stopping with supply scarcity and stochastic cover price. only on preregistered incremental value.
- Gate: Reject if holdout cost savings are below 5% or any mandated deadline is missed.

## Stage 3 — controlled shadow evaluation (weeks 9–12)
- Measure resolved failure days, total cure cost, forced buy-in count, missed deadline, tail loss., the relevant capacity constraints and all-in implementation cost.
- Replace illustrative 24-month ROI (-50% to 100%) with source-backed measured economics or explicitly retain uncertainty.
- Gate: independent risk/compliance review, adequate tail robustness, reproducibility evidence.

## Deferred production
Requires separate feature PR, CI, audit controls, monitoring, rollback and human authorization. No live trading or private data is authorized by this package.
