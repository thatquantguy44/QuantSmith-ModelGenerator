# EVALS — Synthetic Borrow Supply via Options Parity
**Not yet run.**
- **Hypothesis:** Parity-adjusted replication reduces funding cost for eligible positions after dividends and exercise risk.
- **Comparator:** physical borrow only.
- **Candidate:** implied financing via corrected put-call parity; later assess mixed-integer derivative replication with exercise constraints.
- **Economic metrics:** executable financing benefit, hedge error, margin and basis risk.
- **Falsification:** reject the candidate if it fails to deliver economically material improvement against baseline after full costs, legal constraints, risk limits and multiple-testing checks.
- **Time safety:** use source `available_at` <= decision clock, embargo for overlapping forward outcomes, preserve revisions, avoid survivor selection.
- **Stress:** American exercise and forecast-dividend mismatch.
- **Robustness:** resample market events with appropriate block bootstrap, vary spreads, fees, balance sheet, collateral, reporting lag and execution availability.
- **Acceptance:** SPEC AC-001..AC-005 must have deterministic fixtures, test names and independent reviewer signoff.
- **Negative-result rule:** publish a failed or inconclusive hypothesis with exact limitations rather than optimizing the story after the fact.
**No calculated results or confidence bounds are claimed.**
