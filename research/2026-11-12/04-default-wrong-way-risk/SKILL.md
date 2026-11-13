---
name: default-wrong-way-risk
description: "Reproducible financing research: Borrower Default Wrong-Way Risk Optimization."
---
# Reusable skill — Borrower Default Wrong-Way Risk Optimization
## Trigger
When deciding how to **price borrower limits, haircut and contingent indemnification**.
## Preconditions
Authoritative SPEC/PLAN, confirmed timestamp and unit, authorized access to Counterparty credit, collateral, contract closeout provisions, stress price and liquidity history, approved risk and cost model.
## Method
1. Restate hypothesis and observable decision.
2. Build immutable source and licensing ledger; reject inaccessible private data.
3. Create point-in-time synthetic fixture for default-wrong-way-risk; forbid future updates.
4. Rebuild independent PD times static haircut with real costs and legal constraints.
5. Specify correlated default/exposure Monte Carlo, then optionally stochastic-intensity wrong-way closeout with price impact.
6. Run time-split/paired holdout evaluation: stress ES, loss calibration, limits used and risk-adjusted P&L.
7. Stress primary threat: sparse default observations and unidentifiable tail parameters.
8. Write falsification, negative findings and exact run manifest.
9. Update HANDOFF truthfully; request human risk and economic review.
## Output
Proposed `run_manifest.json`, `claims.md`, `metrics.json`, `results.md`; none exist yet.
## Reuse
Share time-alignment, economics, source-rights checks and synthetic fixtures with other QMG skills, but keep the domain-specific model scoped here.
