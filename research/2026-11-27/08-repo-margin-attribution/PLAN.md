# PLAN — Marginal Initial-Margin Attribution for Repo Netting Sets
**QMG-20261127-08 | A — Securities finance | US cleared repo / approved global netting sets | proposal only**
## Architecture
Source adapter → vintage/rights registry → repo-margin-attribution state builder → baseline → candidate → matched economic replay → independent gate. Grain: legal netting set × trade × approved portfolio snapshot. Data: trade exposures, margin calculator/version, collateral requirements, legal partitions, realized margin changes. Timing: snapshot and calculator version known at allocation; never use future netting trades.

## Model sequence
Baseline pro-rata gross notional allocation; candidate sampled Shapley attribution with reconciliation; advanced stratified permutation/control variate plus incremental risk budget. Estimate on rolling training windows, tune only validation, freeze holdout and cost assumptions. Build a no-action comparator when capacity uncertain. Primary risk: black-box margin nonlinearities, allocation instability; hypothetical allocations not actual margin calls. No private data in repo.

## Proposed typed functions
load(as_of, source_ids)->versioned_rows; state(rows, cutoff)->repo-margin-attribution decision states; baseline(states)->actions; candidate(states, config)->actions; evaluate(actions, outcomes)->reconciliation error, holdout marginal-cost error, allocation stability, compute time; validate() rejects empty coalition; hedged negative marginal; isolated netting sets; order invariance. Map functions to REQ-001–004 and NFR-001/002; report missing inputs rather than fabricate. $300m modeled margin-sensitive inventory equivalent × 5 bps estimated allocation efficiency = $150k/year; attribution itself books no savings. Check actual costs/available liquidity before shadow. No implementation yet.
