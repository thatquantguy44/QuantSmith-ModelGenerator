# TASKS — Short Interest versus Securities Loan Utilization State Decomposition
**QMG-20261127-05 | A — Securities finance | US exchange-listed equities | proposal only**
All tasks not started; data/rights gate BLOCKED until approved.
| ID | Work | Completion evidence |
|---|---|---|
| T01 | Acquire permitted issuer × share class × trading day / short-interest publication data and clocks | AC-001 source manifest; ingest FINRA publication after 4:40 p.m. ET or later actual receipt; trade next eligible session |
| T02 | Build synthetic fixture and constraint checks | AC-001/005 tests: synthetic split, delayed publication, denominator near zero, shuffled release labels |
| T03 | Implement autoregression on utilization and market returns | AC-002 hand-calculated baseline reconciliation |
| T04 | Implement constrained state-space model with delayed SI observation | AC-003 deterministic result and pinned config |
| T05 | Compare hierarchical particle filter with split-adjusted latent demand/supply regime | AC-003 ablation, only if justified |
| T06 | Frozen matched holdout | AC-004 MAE, calibration, supply/demand label precision on verified events and confidence intervals |
| T07 | Stress short interest is not total loans, coverage differs by vendor and share class | AC-005 negative tests; ≥10% MAE reduction, bootstrap lower bound positive; abstain when components unidentifiable |
| T08 | Review capacity, legal and source rights | AC-006 independent signoff and no confidential outputs |
No named test is implemented; done only after evidence and review.
