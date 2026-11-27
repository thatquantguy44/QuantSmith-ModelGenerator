# TASKS — US Mortgage Origination Fall-Through and Rate-Lock Convexity
**QMG-20261127-19 | B — Domestic/global markets | US residential mortgage origination and rates | proposal only**
All tasks not started; data/rights gate BLOCKED until approved.
| ID | Work | Completion evidence |
|---|---|---|
| T01 | Acquire permitted application/lock × decision date; public HMDA annual cohort only data and clocks | AC-001 source manifest; public HMDA only after annual release; private locks timestamped before hedge; no demographic targeting |
| T02 | Build synthetic fixture and constraint checks | AC-001/005 tests: withdrawals, lock extension, refi regime, future rate and applicant privacy |
| T03 | Implement fixed pull-through by stage and loan type | AC-002 hand-calculated baseline reconciliation |
| T04 | Implement competing-risk duration model with rate gap | AC-003 deterministic result and pinned config |
| T05 | Compare joint hazard and convexity hedge with correlated fallout scenarios | AC-003 ablation, only if justified |
| T06 | Frozen matched holdout | AC-004 hedge error, pull-through calibration, bias, cost and residual duration and confidence intervals |
| T07 | Stress HMDA lacks lock-level timestamps; public model cannot establish live hedge efficacy | AC-005 negative tests; ≥10% hedge RMSE reduction at equal costs; no use of protected attributes for decisions |
| T08 | Review capacity, legal and source rights | AC-006 independent signoff and no confidential outputs |
No named test is implemented; done only after evidence and review.
