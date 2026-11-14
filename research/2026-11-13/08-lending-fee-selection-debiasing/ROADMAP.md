# ROADMAP — Securities-Lending Fee Observability & Selection-Bias Corrector
## Stage 0 — evidence feasibility (weeks 1–2)
- Validate public data meaning, historical vintages, publication lag and any commercial license for **US/global securities lending benchmarks**.
- Confirm action/market legal constraints, unit conventions and security × lending day × vendor/contributor population.
- Gate: stop if input authorization, comparable baseline or event-time record is unavailable.

## Stage 1 — reproducible baseline (weeks 3–4)
- Create synthetic event fixtures with adverse missing/revision scenarios.
- Implement Daily equally weighted or outstanding-value-weighted observed market fees. and hard feasibility tests.
- Gate: AC-001, AC-002, AC-005.

## Stage 2 — candidate science (weeks 5–8)
- Implement Doubly robust weighting with overlap and selection-sensitivity intervals., compare matched chronological holdouts, audit Missing-not-at-random selection cannot be identified from executed loans alone; confidence intervals can be falsely narrow..
- Consider Bayesian selection model with unverifiable missing-not-at-random stress bounds. only on preregistered incremental value.
- Gate: Reject if cross-contributor MAE reduction <10% or intervals under-cover known withheld contributions.

## Stage 3 — controlled shadow evaluation (weeks 9–12)
- Measure cross-contributor benchmark error, interval coverage, abstention, quote drift, market breadth coverage., the relevant capacity constraints and all-in implementation cost.
- Replace illustrative 24-month ROI (-62% to 92%) with source-backed measured economics or explicitly retain uncertainty.
- Gate: independent risk/compliance review, adequate tail robustness, reproducibility evidence.

## Deferred production
Requires separate feature PR, CI, audit controls, monitoring, rollback and human authorization. No live trading or private data is authorized by this package.
