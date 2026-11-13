---
name: repo-term-dislocation
description: "Reproducible financing research: Repo Term Structure Dislocation Engine."
---
# Reusable skill — Repo Term Structure Dislocation Engine
## Trigger
When deciding how to **choose term financing maturity and collateral route**.
## Preconditions
Authoritative SPEC/PLAN, confirmed timestamp and unit, authorized access to Repo rate/tenor quotes, SOFR, collateral CUSIP, haircut, balance-sheet dates, approved risk and cost model.
## Method
1. Restate hypothesis and observable decision.
2. Build immutable source and licensing ledger; reject inaccessible private data.
3. Create point-in-time synthetic fixture for repo-term-dislocation; forbid future updates.
4. Rebuild overnight funding rollover with real costs and legal constraints.
5. Specify security-aware no-arbitrage term curve, then optionally regime-switching state-space financing optimization.
6. Run time-split/paired holdout evaluation: after-cost funding savings, basis convergence, risk and drawdown.
7. Stress primary threat: indicative prices and bid/ask execution mismatch.
8. Write falsification, negative findings and exact run manifest.
9. Update HANDOFF truthfully; request human risk and economic review.
## Output
Proposed `run_manifest.json`, `claims.md`, `metrics.json`, `results.md`; none exist yet.
## Reuse
Share time-alignment, economics, source-rights checks and synthetic fixtures with other QMG skills, but keep the domain-specific model scoped here.
