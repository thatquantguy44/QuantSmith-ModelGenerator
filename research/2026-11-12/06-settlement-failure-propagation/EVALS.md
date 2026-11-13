# EVALS — Collateral Settlement Failure Propagation
**Not yet run.**
- **Hypothesis:** Network preventive routing reduces aggregate failed obligations relative to isolated fail scoring.
- **Comparator:** FIFO escalation by individual settlement.
- **Candidate:** directed graph contagion replay; later assess stochastic hypergraph scheduling and recovery routing.
- **Economic metrics:** cascade size, failed notional, recovery time and funding cost.
- **Falsification:** reject the candidate if it fails to deliver economically material improvement against baseline after full costs, legal constraints, risk limits and multiple-testing checks.
- **Time safety:** use source `available_at` <= decision clock, embargo for overlapping forward outcomes, preserve revisions, avoid survivor selection.
- **Stress:** incomplete external dependencies and cross-entity visibility.
- **Robustness:** resample market events with appropriate block bootstrap, vary spreads, fees, balance sheet, collateral, reporting lag and execution availability.
- **Acceptance:** SPEC AC-001..AC-005 must have deterministic fixtures, test names and independent reviewer signoff.
- **Negative-result rule:** publish a failed or inconclusive hypothesis with exact limitations rather than optimizing the story after the fact.
**No calculated results or confidence bounds are claimed.**
