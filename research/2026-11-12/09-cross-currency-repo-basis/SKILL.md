---
name: cross-currency-repo-basis
description: "Reproducible financing research: Cross-Currency Repo Basis Optimization."
---
# Reusable skill — Cross-Currency Repo Basis Optimization
## Trigger
When deciding how to **choose FX-hedged financing currency and legal collateral path**.
## Preconditions
Authoritative SPEC/PLAN, confirmed timestamp and unit, authorized access to FX swaps, currencies, tenor rates, haircuts, FX settlements, taxes, legal eligibility, approved risk and cost model.
## Method
1. Restate hypothesis and observable decision.
2. Build immutable source and licensing ledger; reject inaccessible private data.
3. Create point-in-time synthetic fixture for cross-currency-repo-basis; forbid future updates.
4. Rebuild domestic collateral and repo only with real costs and legal constraints.
5. Specify covered-interest-parity-adjusted funding network, then optionally stochastic multi-currency funding and collateral flow.
6. Run time-split/paired holdout evaluation: hedged carry, capacity, FX basis risk and all-in spread.
7. Stress primary threat: false arbitrage from stale asynchronous or inaccessible quotes.
8. Write falsification, negative findings and exact run manifest.
9. Update HANDOFF truthfully; request human risk and economic review.
## Output
Proposed `run_manifest.json`, `claims.md`, `metrics.json`, `results.md`; none exist yet.
## Reuse
Share time-alignment, economics, source-rights checks and synthetic fixtures with other QMG skills, but keep the domain-specific model scoped here.
