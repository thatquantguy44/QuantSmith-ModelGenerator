# TASKS — Global Pension Contribution-Aware Rebalancing with Trading Frictions
**QMG-20261127-20 | B — Domestic/global markets | US, UK, Canada and Netherlands institutional allocation | proposal only**
All tasks not started; data/rights gate BLOCKED until approved.
| ID | Work | Completion evidence |
|---|---|---|
| T01 | Acquire permitted plan type × asset class × month / public annual country aggregates data and clocks | AC-001 source manifest; only annual OECD releases for long-run calibration; approved plan cashflows known before month-end decisions |
| T02 | Build synthetic fixture and constraint checks | AC-001/005 tests: cash outflow shock, policy band breach, zero liquidity, stale NAV |
| T03 | Implement calendar rebalancing with identical cashflow forecast and policy constraints | AC-002 hand-calculated baseline reconciliation |
| T04 | Implement convex no-trade-band optimizer | AC-003 deterministic result and pinned config |
| T05 | Compare multi-period stochastic control using uncertain benefit payments | AC-003 ablation, only if justified |
| T06 | Frozen matched holdout | AC-004 net transaction costs, tracking error, liquidity shortfalls, turnover and confidence intervals |
| T07 | Stress OECD aggregates cannot reveal real plan trades; benefit schedules private | AC-005 negative tests; ≥10% cost reduction at noninferior tracking risk and zero cash deficits |
| T08 | Review capacity, legal and source rights | AC-006 independent signoff and no confidential outputs |
No named test is implemented; done only after evidence and review.
