# TASKS — Repo Maturity Mismatch Early-Warning via Survival Cash Ladders
**QMG-20261127-10 | A — Securities finance | US and European matched-book secured funding | proposal only**
All tasks not started; data/rights gate BLOCKED until approved.
| ID | Work | Completion evidence |
|---|---|---|
| T01 | Acquire permitted repo trade × maturity bucket × daily snapshot data and clocks | AC-001 source manifest; decision before maturity; only renewals confirmed by snapshot; outcomes as labels |
| T02 | Build synthetic fixture and constraint checks | AC-001/005 tests: no renewals in stress, maturity concentration, missing confirmations |
| T03 | Implement contractual maturity ladder with fixed stress rollover percentage | AC-002 hand-calculated baseline reconciliation |
| T04 | Implement competing-risk survival and calibrated gap scenarios | AC-003 deterministic result and pinned config |
| T05 | Compare hierarchical regime-dependent survival with correlated nonrenewal | AC-003 ablation, only if justified |
| T06 | Frozen matched holdout | AC-004 Brier score, cash-gap quantile coverage, warning lead time, reserve cost and confidence intervals |
| T07 | Stress censoring of renewals and structural shifts; predicted rollover not assured liquidity | AC-005 negative tests; ≥10% Brier improvement and adequate 95% gap interval coverage; no uncommitted cash counted as guaranteed |
| T08 | Review capacity, legal and source rights | AC-006 independent signoff and no confidential outputs |
No named test is implemented; done only after evidence and review.
