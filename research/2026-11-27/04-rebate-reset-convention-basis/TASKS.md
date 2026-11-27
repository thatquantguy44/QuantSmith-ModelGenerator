# TASKS — Benchmark Reset Convention Basis in Securities Loan Rebates
**QMG-20261127-04 | A — Securities finance | USD and GBP cash-collateral lending | proposal only**
All tasks not started; data/rights gate BLOCKED until approved.
| ID | Work | Completion evidence |
|---|---|---|
| T01 | Acquire permitted contract × accrual date × fixing vintage data and clocks | AC-001 source manifest; fixings available only after publication; project unknown future rates as scenarios, never realized inputs |
| T02 | Build synthetic fixture and constraint checks | AC-001/005 tests: weekend accrual, leap day, missing fixing, negative rate, different day counts |
| T03 | Implement same-day benchmark with standard day count | AC-002 hand-calculated baseline reconciliation |
| T04 | Implement deterministic reset/compounding convention engine | AC-003 deterministic result and pinned config |
| T05 | Compare scenario curve and hedge sensitivity under competing reset clocks | AC-003 ablation, only if justified |
| T06 | Frozen matched holdout | AC-004 reconciliation USD, residual basis, projected mismatch, fixture accuracy and confidence intervals |
| T07 | Stress ambiguous fallback language and publication lag; legacy terms not inferable from index name | AC-005 negative tests; 100% golden convention fixtures and ≥95% explained confirmed discrepancies; no unexplained sign errors |
| T08 | Review capacity, legal and source rights | AC-006 independent signoff and no confidential outputs |
No named test is implemented; done only after evidence and review.
