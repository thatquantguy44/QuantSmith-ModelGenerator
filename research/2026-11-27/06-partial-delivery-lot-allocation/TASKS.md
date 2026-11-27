# TASKS — Partial Securities Delivery Allocation under Minimum Lot Rules
**QMG-20261127-06 | A — Securities finance | US and European securities settlement | proposal only**
All tasks not started; data/rights gate BLOCKED until approved.
| ID | Work | Completion evidence |
|---|---|---|
| T01 | Acquire permitted security × settlement instruction × cutoff snapshot data and clocks | AC-001 source manifest; before each cutoff with confirmed deliverable stock; pending receipts excluded |
| T02 | Build synthetic fixture and constraint checks | AC-001/005 tests: lot above remainder; negative inventory; all-or-nothing flag; delayed acknowledgement |
| T03 | Implement earliest-deadline-first full delivery | AC-002 hand-calculated baseline reconciliation |
| T04 | Implement integer allocation with minimum partial sizes | AC-003 deterministic result and pinned config |
| T05 | Compare two-stage stochastic delivery with confirmed receipts and recourse | AC-003 ablation, only if justified |
| T06 | Frozen matched holdout | AC-004 weighted undelivered shares, net fail fees, message count, missed cutoffs and confidence intervals |
| T07 | Stress partial processing overhead and legal restrictions differ by venue | AC-005 negative tests; ≥10% lower weighted unmet shares and non-increasing net costs; zero impermissible partials |
| T08 | Review capacity, legal and source rights | AC-006 independent signoff and no confidential outputs |
No named test is implemented; done only after evidence and review.
