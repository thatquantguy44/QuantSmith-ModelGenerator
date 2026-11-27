# TASKS — Marginal Initial-Margin Attribution for Repo Netting Sets
**QMG-20261127-08 | A — Securities finance | US cleared repo / approved global netting sets | proposal only**
All tasks not started; data/rights gate BLOCKED until approved.
| ID | Work | Completion evidence |
|---|---|---|
| T01 | Acquire permitted legal netting set × trade × approved portfolio snapshot data and clocks | AC-001 source manifest; snapshot and calculator version known at allocation; never use future netting trades |
| T02 | Build synthetic fixture and constraint checks | AC-001/005 tests: empty coalition; hedged negative marginal; isolated netting sets; order invariance |
| T03 | Implement pro-rata gross notional allocation | AC-002 hand-calculated baseline reconciliation |
| T04 | Implement sampled Shapley attribution with reconciliation | AC-003 deterministic result and pinned config |
| T05 | Compare stratified permutation/control variate plus incremental risk budget | AC-003 ablation, only if justified |
| T06 | Frozen matched holdout | AC-004 reconciliation error, holdout marginal-cost error, allocation stability, compute time and confidence intervals |
| T07 | Stress black-box margin nonlinearities, allocation instability; hypothetical allocations not actual margin calls | AC-005 negative tests; relative error ≤1% reconciliation and ≥10% marginal MAE reduction; no illegal netting |
| T08 | Review capacity, legal and source rights | AC-006 independent signoff and no confidential outputs |
No named test is implemented; done only after evidence and review.
