# ROADMAP — Treasury Clearing Access-Path & Duplicate-Margin Optimizer
## Stage 0 — evidence feasibility (weeks 1–2)
- Validate public data meaning, historical vintages, publication lag and any commercial license for **United States; cleared cash Treasury and repo**.
- Confirm action/market legal constraints, unit conventions and trade × eligible clearing access path × decision timestamp.
- Gate: stop if input authorization, comparable baseline or event-time record is unavailable.

## Stage 1 — reproducible baseline (weeks 3–4)
- Create synthetic event fixtures with adverse missing/revision scenarios.
- Implement Minimize executable repo rate ignoring path-specific costs, after validating that every route is eligible. and hard feasibility tests.
- Gate: AC-001, AC-002, AC-005.

## Stage 2 — candidate science (weeks 5–8)
- Implement Mixed-integer convex routing with separate margin, settlement and liquidity shadow prices., compare matched chronological holdouts, audit Clearing rule exemptions and netting eligibility vary; estimated margin offsets could be nonportable across entities..
- Consider Stochastic two-stage CCP-margin and default-fund planning with cross-netting robustness. only on preregistered incremental value.
- Gate: Reject if simulated net savings are below 2 bps of affected financing notional or vanish under independently validated margin rules.

## Stage 3 — controlled shadow evaluation (weeks 9–12)
- Measure USD all-in funding cost, dollar liquidity encumbrance, margin stress p99, ineligible route count, rejection rate., the relevant capacity constraints and all-in implementation cost.
- Replace illustrative 24-month ROI (-43% to 121%) with source-backed measured economics or explicitly retain uncertainty.
- Gate: independent risk/compliance review, adequate tail robustness, reproducibility evidence.

## Deferred production
Requires separate feature PR, CI, audit controls, monitoring, rollback and human authorization. No live trading or private data is authorized by this package.
