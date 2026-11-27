# TASKS — Countercyclical Repo Haircut Adjustment with Hysteresis
**QMG-20261127-02 | A — Securities finance | US/EU non-cleared secured funding | proposal only**
All tasks not started; data/rights gate BLOCKED until approved.
| ID | Work | Completion evidence |
|---|---|---|
| T01 | Acquire permitted collateral class × legal agreement × risk day data and clocks | AC-001 source manifest; previously published volatility/rates, signed terms before risk decision |
| T02 | Build synthetic fixture and constraint checks | AC-001/005 tests: mandatory floor jump; fast crash; prohibited haircut decrease |
| T03 | Implement rolling volatility haircut with same mandatory floors | AC-002 hand-calculated baseline reconciliation |
| T04 | Implement hysteretic threshold controller | AC-003 deterministic result and pinned config |
| T05 | Compare robust stochastic policy with joint liquidation and funding shocks | AC-003 ablation, only if justified |
| T06 | Frozen matched holdout | AC-004 p99 incremental margin call, expected shortfall of closeout, floor breaches and confidence intervals |
| T07 | Stress selection by counterparty and tail scarcity; slower hikes may worsen credit losses | AC-005 negative tests; ≥10% reduction in p99 call; upper 95% bound for incremental ES≤approved tolerance; zero floor violations |
| T08 | Review capacity, legal and source rights | AC-006 independent signoff and no confidential outputs |
No named test is implemented; done only after evidence and review.
