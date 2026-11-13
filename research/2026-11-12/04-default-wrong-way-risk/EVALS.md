# EVALS — Borrower Default Wrong-Way Risk Optimization
**Not yet run.**
- **Hypothesis:** Joint default-exposure modeling finds stressed loss missed by independent PD/haircut rules.
- **Comparator:** independent PD times static haircut.
- **Candidate:** correlated default/exposure Monte Carlo; later assess stochastic-intensity wrong-way closeout with price impact.
- **Economic metrics:** stress ES, loss calibration, limits used and risk-adjusted P&L.
- **Falsification:** reject the candidate if it fails to deliver economically material improvement against baseline after full costs, legal constraints, risk limits and multiple-testing checks.
- **Time safety:** use source `available_at` <= decision clock, embargo for overlapping forward outcomes, preserve revisions, avoid survivor selection.
- **Stress:** sparse default observations and unidentifiable tail parameters.
- **Robustness:** resample market events with appropriate block bootstrap, vary spreads, fees, balance sheet, collateral, reporting lag and execution availability.
- **Acceptance:** SPEC AC-001..AC-005 must have deterministic fixtures, test names and independent reviewer signoff.
- **Negative-result rule:** publish a failed or inconclusive hypothesis with exact limitations rather than optimizing the story after the fact.
**No calculated results or confidence bounds are claimed.**
