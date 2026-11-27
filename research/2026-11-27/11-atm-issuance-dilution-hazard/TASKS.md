# TASKS — US Small-Cap ATM Equity Issuance Dilution Hazard
**QMG-20261127-11 | B — Domestic/global markets | US small-cap equities | proposal only**
All tasks not started; data/rights gate BLOCKED until approved.
| ID | Work | Completion evidence |
|---|---|---|
| T01 | Acquire permitted issuer CIK × accession × trading day data and clocks | AC-001 source manifest; first dissemination of each accession, next tradable session; quarter issuance outcomes after filings |
| T02 | Build synthetic fixture and constraint checks | AC-001/005 tests: authorization without issuance; reverse split; delisting; duplicate supplement |
| T03 | Implement cash-runway and market-cap logistic hazard | AC-002 hand-calculated baseline reconciliation |
| T04 | Implement survival model with disclosed program capacity and competing financing events | AC-003 deterministic result and pinned config |
| T05 | Compare hierarchical joint issuance-size and event-return model | AC-003 ablation, only if justified |
| T06 | Frozen matched holdout | AC-004 Brier, dilution MAE, event return attribution, false-alert rate and confidence intervals |
| T07 | Stress ATM authorization is not execution; reverse splits, delayed quarterly reports and failed issuers | AC-005 negative tests; ≥10% Brier improvement; precision improvement at fixed recall; no surviving-only universe |
| T08 | Review capacity, legal and source rights | AC-006 independent signoff and no confidential outputs |
No named test is implemented; done only after evidence and review.
