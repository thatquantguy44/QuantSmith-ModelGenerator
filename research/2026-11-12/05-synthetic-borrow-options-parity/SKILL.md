---
name: synthetic-borrow-options-parity
description: "Reproducible financing research: Synthetic Borrow Supply via Options Parity."
---
# Reusable skill — Synthetic Borrow Supply via Options Parity
## Trigger
When deciding how to **choose physical versus synthetic financing exposure**.
## Preconditions
Authoritative SPEC/PLAN, confirmed timestamp and unit, authorized access to Options bid/ask, dividends, loan fees, stock price, funding, margin and assignment mechanics, approved risk and cost model.
## Method
1. Restate hypothesis and observable decision.
2. Build immutable source and licensing ledger; reject inaccessible private data.
3. Create point-in-time synthetic fixture for synthetic-borrow-options-parity; forbid future updates.
4. Rebuild physical borrow only with real costs and legal constraints.
5. Specify implied financing via corrected put-call parity, then optionally mixed-integer derivative replication with exercise constraints.
6. Run time-split/paired holdout evaluation: executable financing benefit, hedge error, margin and basis risk.
7. Stress primary threat: American exercise and forecast-dividend mismatch.
8. Write falsification, negative findings and exact run manifest.
9. Update HANDOFF truthfully; request human risk and economic review.
## Output
Proposed `run_manifest.json`, `claims.md`, `metrics.json`, `results.md`; none exist yet.
## Reuse
Share time-alignment, economics, source-rights checks and synthetic fixtures with other QMG skills, but keep the domain-specific model scoped here.
