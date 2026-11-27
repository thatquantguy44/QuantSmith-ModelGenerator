# TASKS — Swiss Franc Conditional Safe-Haven Hedge Reliability
**QMG-20261127-13 | B — Domestic/global markets | Switzerland, euro area and global risk portfolios | proposal only**
All tasks not started; data/rights gate BLOCKED until approved.
| ID | Work | Completion evidence |
|---|---|---|
| T01 | Acquire permitted currency pair × day × decision timestamp data and clocks | AC-001 source manifest; daily decisions after all required markets close, execute next quote; no revised intervention data |
| T02 | Build synthetic fixture and constraint checks | AC-001/005 tests: crisis placebo, asynchronous close, stale rate, one-event dominance |
| T03 | Implement fixed CHF allocation with equal carry budget | AC-002 hand-calculated baseline reconciliation |
| T04 | Implement threshold quantile regression on risk-state proxies | AC-003 deterministic result and pinned config |
| T05 | Compare hidden Markov state model with robust scenario hedge | AC-003 ablation, only if justified |
| T06 | Frozen matched holdout | AC-004 expected shortfall, carry, hedge hit rate, turnover and confidence intervals |
| T07 | Stress safe-haven relation unstable; overlapping global closes and intervention confounding | AC-005 negative tests; ≥10% ES improvement at matched carry and acceptable return sacrifice; robust to crisis leave-one-out |
| T08 | Review capacity, legal and source rights | AC-006 independent signoff and no confidential outputs |
No named test is implemented; done only after evidence and review.
