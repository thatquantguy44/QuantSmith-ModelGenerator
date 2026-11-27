# TASKS — Exchange Metals Off-Warrant Inventory and Calendar-Spread Scarcity
**QMG-20261127-16 | B — Domestic/global markets | London Metal Exchange global base metals | proposal only**
All tasks not started; data/rights gate BLOCKED until approved.
| ID | Work | Completion evidence |
|---|---|---|
| T01 | Acquire permitted metal × warehouse region × publication date data and clocks | AC-001 source manifest; free data only after actual T+3 or current verified delay; paid T+1 separately; execute next quote |
| T02 | Build synthetic fixture and constraint checks | AC-001/005 tests: T+3 lag versus T+1 contamination; transfers double counted; contract roll |
| T03 | Implement on-warrant stocks and curve momentum | AC-002 hand-calculated baseline reconciliation |
| T04 | Implement distributed-lag inventory/curve model | AC-003 deterministic result and pinned config |
| T05 | Compare latent location-transfer state model with inventory conservation | AC-003 ablation, only if justified |
| T06 | Frozen matched holdout | AC-004 MAE, curve sign accuracy, net spread P&L, capacity and confidence intervals |
| T07 | Stress warrant cancellations can be relocation not end demand; data rights and warehouse incentives | AC-005 negative tests; ≥10% MAE reduction; positive net spread benefit after storage/roll/fees before trading gate |
| T08 | Review capacity, legal and source rights | AC-006 independent signoff and no confidential outputs |
No named test is implemented; done only after evidence and review.
