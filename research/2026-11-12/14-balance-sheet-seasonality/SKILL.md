---
name: balance-sheet-seasonality
description: "Reproducible financing research: Balance-Sheet Seasonality Arbitrage."
---
# Reusable skill — Balance-Sheet Seasonality Arbitrage
## Trigger
When deciding how to **choose funding tenor and capacity reserves around reporting dates**.
## Preconditions
Authoritative SPEC/PLAN, confirmed timestamp and unit, authorized access to Repo spread term structure, settlement calendar, quarter-end dates, financing usage, approved risk and cost model.
## Method
1. Restate hypothesis and observable decision.
2. Build immutable source and licensing ledger; reject inaccessible private data.
3. Create point-in-time synthetic fixture for balance-sheet-seasonality; forbid future updates.
4. Rebuild constant overnight-roll financing with real costs and legal constraints.
5. Specify calendar event study with capacity-aware optimization, then optionally stochastic dynamic capacity control under regime variation.
6. Run time-split/paired holdout evaluation: holdout funding cost, stress liquidity, rollover risk and drawdown.
7. Stress primary threat: well-known quarter-end effects may already be fully priced.
8. Write falsification, negative findings and exact run manifest.
9. Update HANDOFF truthfully; request human risk and economic review.
## Output
Proposed `run_manifest.json`, `claims.md`, `metrics.json`, `results.md`; none exist yet.
## Reuse
Share time-alignment, economics, source-rights checks and synthetic fixtures with other QMG skills, but keep the domain-specific model scoped here.
