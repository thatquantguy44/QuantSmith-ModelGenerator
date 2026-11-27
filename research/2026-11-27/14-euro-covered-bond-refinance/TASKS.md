# TASKS — Euro Bank Covered versus Unsecured Refinancing Maturity Wall
**QMG-20261127-14 | B — Domestic/global markets | Euro area bank credit | proposal only**
All tasks not started; data/rights gate BLOCKED until approved.
| ID | Work | Completion evidence |
|---|---|---|
| T01 | Acquire permitted issuer × liability class × reporting vintage data and clocks | AC-001 source manifest; filing dissemination before monthly decision; issue prices after actual issuance as outcomes |
| T02 | Build synthetic fixture and constraint checks | AC-001/005 tests: no issuance censoring; called debt; revised maturities; currency mismatch |
| T03 | Implement rating, duration and sovereign spread regression | AC-002 hand-calculated baseline reconciliation |
| T04 | Implement panel maturity-wall regression with competing liability type | AC-003 deterministic result and pinned config |
| T05 | Compare structural joint issuance choice and spread state model | AC-003 ablation, only if justified |
| T06 | Frozen matched holdout | AC-004 spread MAE, gap error, coverage, class-adjusted residual and confidence intervals |
| T07 | Stress ECB aggregates do not establish individual maturity terms; selection into issuance | AC-005 negative tests; ≥10% MAE improvement on held-out banks/quarters; signs stable under rate controls |
| T08 | Review capacity, legal and source rights | AC-006 independent signoff and no confidential outputs |
No named test is implemented; done only after evidence and review.
