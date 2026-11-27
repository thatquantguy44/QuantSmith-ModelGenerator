# TASKS — Accrual Cash-Conversion Reversal with XBRL Restatement Lineage
**QMG-20261127-15 | B — Domestic/global markets | US and foreign SEC reporting equities | proposal only**
All tasks not started; data/rights gate BLOCKED until approved.
| ID | Work | Completion evidence |
|---|---|---|
| T01 | Acquire permitted issuer CIK × fiscal quarter × filing accession × tag data and clocks | AC-001 source manifest; first filing acceptance/dissemination, with later amended accession separate; decisions next session |
| T02 | Build synthetic fixture and constraint checks | AC-001/005 tests: YTD-to-quarter conversion, duplicate tag contexts, unit mismatch, 10-K/A future amendment |
| T03 | Implement total accrual ratio plus sector and size | AC-002 hand-calculated baseline reconciliation |
| T04 | Implement sparse panel with accession-aware working-capital features | AC-003 deterministic result and pinned config |
| T05 | Compare hierarchical accounting graph with semantic tag mapping and abstention | AC-003 ablation, only if justified |
| T06 | Frozen matched holdout | AC-004 cash-flow MAE, tag mapping precision, forecast IC, coverage and confidence intervals |
| T07 | Stress taxonomy changes, YTD versus quarter flows, acquisition effects, lookahead from amendments | AC-005 negative tests; ≥10% MAE improvement; ≥98% mapping precision on hand labels; abstain on ambiguity |
| T08 | Review capacity, legal and source rights | AC-006 independent signoff and no confidential outputs |
No named test is implemented; done only after evidence and review.
