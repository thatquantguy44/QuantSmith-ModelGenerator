# TASKS — Brazil Reservoir Water Value and Utility Earnings Risk
**QMG-20261127-17 | B — Domestic/global markets | Brazil hydroelectric generation and utility equities | proposal only**
All tasks not started; data/rights gate BLOCKED until approved.
| ID | Work | Completion evidence |
|---|---|---|
| T01 | Acquire permitted ONS subsystem × day × release vintage data and clocks | AC-001 source manifest; only archived public release versions; ONS data may revise; forecast issuance known before decision |
| T02 | Build synthetic fixture and constraint checks | AC-001/005 tests: dry-year holdout, negative storage, future actual inflows, spill |
| T03 | Implement seasonal reservoir percentile and lagged marginal cost | AC-002 hand-calculated baseline reconciliation |
| T04 | Implement simplified stochastic dispatch LP | AC-003 deterministic result and pinned config |
| T05 | Compare multistage stochastic dual dynamic programming with hydrological scenarios | AC-003 ablation, only if justified |
| T06 | Frozen matched holdout | AC-004 marginal cost MAE, reliability, earnings scenario error, feasible dispatch and confidence intervals |
| T07 | Stress physical dispatch simplification, hydrology revision and issuer hedging obscure returns | AC-005 negative tests; ≥10% forecast MAE improvement; no storage/energy balance violations; pricing claims require market access |
| T08 | Review capacity, legal and source rights | AC-006 independent signoff and no confidential outputs |
No named test is implemented; done only after evidence and review.
