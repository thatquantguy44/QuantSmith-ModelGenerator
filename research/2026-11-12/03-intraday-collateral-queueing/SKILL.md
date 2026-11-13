---
name: intraday-collateral-queueing
description: "Reproducible financing research: Intraday Collateral Liquidity Forecasting via Queueing Theory."
---
# Reusable skill — Intraday Collateral Liquidity Forecasting via Queueing Theory
## Trigger
When deciding how to **size buffer and prioritize arriving collateral obligations**.
## Preconditions
Authoritative SPEC/PLAN, confirmed timestamp and unit, authorized access to Intraday margin calls, settlement timestamps, queue lengths, cash/collateral buffers, fails, approved risk and cost model.
## Method
1. Restate hypothesis and observable decision.
2. Build immutable source and licensing ledger; reject inaccessible private data.
3. Create point-in-time synthetic fixture for intraday-collateral-queueing; forbid future updates.
4. Rebuild fixed intraday liquidity reserve with real costs and legal constraints.
5. Specify stochastic queueing and priority model, then optionally model predictive control with chance-constrained service levels.
6. Run time-split/paired holdout evaluation: liquidity buffer cost, p99 delay, shortfalls and failures.
7. Stress primary threat: timestamp quality and hidden queue-priority rules.
8. Write falsification, negative findings and exact run manifest.
9. Update HANDOFF truthfully; request human risk and economic review.
## Output
Proposed `run_manifest.json`, `claims.md`, `metrics.json`, `results.md`; none exist yet.
## Reuse
Share time-alignment, economics, source-rights checks and synthetic fixtures with other QMG skills, but keep the domain-specific model scoped here.
