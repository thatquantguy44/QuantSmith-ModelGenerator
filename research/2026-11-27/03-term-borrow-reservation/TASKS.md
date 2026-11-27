# TASKS — Forward Borrow Capacity Reservation for Committed Term Loans
**QMG-20261127-03 | A — Securities finance | US and European equity stock loan | proposal only**
All tasks not started; data/rights gate BLOCKED until approved.
| ID | Work | Completion evidence |
|---|---|---|
| T01 | Acquire permitted security × owner mandate × commitment vintage data and clocks | AC-001 source manifest; at commitment acceptance or daily reserve review; only confirmed mandates and availability |
| T02 | Build synthetic fixture and constraint checks | AC-001/005 tests: concurrent commitment consumes same shares; owner withdrawal; zero available shares |
| T03 | Implement fixed fraction of expected term draws, subject to same owner rights | AC-002 hand-calculated baseline reconciliation |
| T04 | Implement newsvendor quantile with censored draws and lead times | AC-003 deterministic result and pinned config |
| T05 | Compare multi-period distributionally robust reservation with scenario owner withdrawals | AC-003 ablation, only if justified |
| T06 | Frozen matched holdout | AC-004 shortage shares, realized reservation cost, service coverage, revenue and confidence intervals |
| T07 | Stress historical accepted demand is selected; inventory cannot be promised against unconfirmed availability | AC-005 negative tests; ≥5% lower total cost, no worse fulfillment rate, zero double booking |
| T08 | Review capacity, legal and source rights | AC-006 independent signoff and no confidential outputs |
No named test is implemented; done only after evidence and review.
