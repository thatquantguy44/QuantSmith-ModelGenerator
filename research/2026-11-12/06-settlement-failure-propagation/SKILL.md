---
name: settlement-failure-propagation
description: "Reproducible financing research: Collateral Settlement Failure Propagation."
---
# Reusable skill — Collateral Settlement Failure Propagation
## Trigger
When deciding how to **target the settlement legs whose failure causes the most downstream loss**.
## Preconditions
Authoritative SPEC/PLAN, confirmed timestamp and unit, authorized access to Dependency-linked settlement legs, legal routes, timestamps, collateral and failed instructions, approved risk and cost model.
## Method
1. Restate hypothesis and observable decision.
2. Build immutable source and licensing ledger; reject inaccessible private data.
3. Create point-in-time synthetic fixture for settlement-failure-propagation; forbid future updates.
4. Rebuild FIFO escalation by individual settlement with real costs and legal constraints.
5. Specify directed graph contagion replay, then optionally stochastic hypergraph scheduling and recovery routing.
6. Run time-split/paired holdout evaluation: cascade size, failed notional, recovery time and funding cost.
7. Stress primary threat: incomplete external dependencies and cross-entity visibility.
8. Write falsification, negative findings and exact run manifest.
9. Update HANDOFF truthfully; request human risk and economic review.
## Output
Proposed `run_manifest.json`, `claims.md`, `metrics.json`, `results.md`; none exist yet.
## Reuse
Share time-alignment, economics, source-rights checks and synthetic fixtures with other QMG skills, but keep the domain-specific model scoped here.
