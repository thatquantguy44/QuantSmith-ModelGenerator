# TASKS — Collateral Substitution with Discrete Lot Opportunity Costs
**QMG-20261127-01 | A — Securities finance | US Treasury and European sovereign repo | proposal only**
All tasks not started; data/rights gate BLOCKED until approved.
| ID | Work | Completion evidence |
|---|---|---|
| T01 | Acquire permitted lot × obligation × snapshot data and clocks | AC-001 source manifest; pre-substitution snapshot; confirm replacement settlement before release; no end-day inventory |
| T02 | Build synthetic fixture and constraint checks | AC-001/005 tests: one scarce lot assigned twice; replacement not final; haircut shock; infeasible obligation |
| T03 | Implement cheapest eligible collateral first with same lot and transfer constraints | AC-002 hand-calculated baseline reconciliation |
| T04 | Implement integer min-cost assignment with opportunity-cost duals | AC-003 deterministic result and pinned config |
| T05 | Compare rolling stochastic mixed-integer control with replacement failure recourse | AC-003 ablation, only if justified |
| T06 | Frozen matched holdout | AC-004 net USD carry/transfer cost, excess collateral, breach count, solve time and confidence intervals |
| T07 | Stress solver can suggest illegal or unsettled substitution if pending collateral is counted | AC-005 negative tests; ≥5% lower matched net cost; zero incremental eligibility or coverage violations; p95 solve time within agreed cutoffs |
| T08 | Review capacity, legal and source rights | AC-006 independent signoff and no confidential outputs |
No named test is implemented; done only after evidence and review.
