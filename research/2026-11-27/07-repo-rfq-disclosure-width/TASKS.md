# TASKS — Repo RFQ Disclosure-Width versus Execution Competition
**QMG-20261127-07 | A — Securities finance | US and UK institutional repo | proposal only**
All tasks not started; data/rights gate BLOCKED until approved.
| ID | Work | Completion evidence |
|---|---|---|
| T01 | Acquire permitted RFQ × recipient-count assignment × session data and clocks | AC-001 source manifest; assign before outreach; only historical availability and quote freshness; observe outcomes later |
| T02 | Build synthetic fixture and constraint checks | AC-001/005 tests: assignment imbalance; correlated RFQs; non-executable response; unsupported recipient |
| T03 | Implement fixed approved number of recipients | AC-002 hand-calculated baseline reconciliation |
| T04 | Implement randomized experiment and heterogeneous treatment effects | AC-003 deterministic result and pinned config |
| T05 | Compare constrained contextual bandit only after randomized support and approval | AC-003 ablation, only if justified |
| T06 | Frozen matched holdout | AC-004 all-in cost, fill probability, post-RFQ drift, coverage and latency and confidence intervals |
| T07 | Stress interference across simultaneous RFQs and confidential order exposure; observational comparisons biased | AC-005 negative tests; ≥2% lower cost, positive paired confidence bound; noninferior fills; zero policy breaches |
| T08 | Review capacity, legal and source rights | AC-006 independent signoff and no confidential outputs |
No named test is implemented; done only after evidence and review.
