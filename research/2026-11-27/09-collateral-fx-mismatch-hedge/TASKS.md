# TASKS — Collateral FX Mismatch Hedge under Margin Revaluation
**QMG-20261127-09 | A — Securities finance | USD/EUR/GBP securities finance | proposal only**
All tasks not started; data/rights gate BLOCKED until approved.
| ID | Work | Completion evidence |
|---|---|---|
| T01 | Acquire permitted collateral basket × currency pair × margin day data and clocks | AC-001 source manifest; only FX quotes/eligibility known before margin and hedge cutoff; hedge at next executable quote |
| T02 | Build synthetic fixture and constraint checks | AC-001/005 tests: FX gap, stale collateral quote, hedge illiquidity, mandatory haircut unchanged |
| T03 | Implement static full currency hedge with same collateral and limits | AC-002 hand-calculated baseline reconciliation |
| T04 | Implement scenario expected-shortfall hedge sizing | AC-003 deterministic result and pinned config |
| T05 | Compare multi-period robust hedge with FX/collateral joint tails | AC-003 ablation, only if justified |
| T06 | Frozen matched holdout | AC-004 margin call ES, hedge slippage, capital/FX residual, hard constraints and confidence intervals |
| T07 | Stress hedges may not qualify as collateral or reduce regulatory haircut; joint FX/security tails unstable | AC-005 negative tests; ≥10% lower ES with total costs reported, no legal/floor violations |
| T08 | Review capacity, legal and source rights | AC-006 independent signoff and no confidential outputs |
No named test is implemented; done only after evidence and review.
