---
name: financing-execution-shortfall
description: "Reproducible financing research: Financing Execution Shortfall Model."
---
# Reusable skill — Financing Execution Shortfall Model
## Trigger
When deciding how to **diagnose where quoted financing economics leak before completed settlement**.
## Preconditions
Authoritative SPEC/PLAN, confirmed timestamp and unit, authorized access to Timestamped RFQs, quotes, fill/rejects, booked fees, market moves and settlement, approved risk and cost model.
## Method
1. Restate hypothesis and observable decision.
2. Build immutable source and licensing ledger; reject inaccessible private data.
3. Create point-in-time synthetic fixture for financing-execution-shortfall; forbid future updates.
4. Rebuild executed spread minus indicative quote with real costs and legal constraints.
5. Specify cost-inclusive execution shortfall event ledger, then optionally matched counterfactual execution-policy evaluator.
6. Run time-split/paired holdout evaluation: bps slippage, recovered P&L, latency and fill rate.
7. Stress primary threat: quotes may be non-executable; client selection creates bias.
8. Write falsification, negative findings and exact run manifest.
9. Update HANDOFF truthfully; request human risk and economic review.
## Output
Proposed `run_manifest.json`, `claims.md`, `metrics.json`, `results.md`; none exist yet.
## Reuse
Share time-alignment, economics, source-rights checks and synthetic fixtures with other QMG skills, but keep the domain-specific model scoped here.
