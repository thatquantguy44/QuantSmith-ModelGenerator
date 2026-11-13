# EVALS — Loan Recall Early-Exercise Boundary
**Not yet run.**
- **Hypothesis:** Owner-specific early-exercise states predict recall timing and lower replacement exposure.
- **Comparator:** constant owner-specific recall probability.
- **Candidate:** constrained survival and stopping model; later assess least-squares Monte Carlo owner exercise policy.
- **Economic metrics:** recall warning, replacement cost, calibration and fail prevention.
- **Falsification:** reject the candidate if it fails to deliver economically material improvement against baseline after full costs, legal constraints, risk limits and multiple-testing checks.
- **Time safety:** use source `available_at` <= decision clock, embargo for overlapping forward outcomes, preserve revisions, avoid survivor selection.
- **Stress:** governance and fiduciary rights cannot be traded away.
- **Robustness:** resample market events with appropriate block bootstrap, vary spreads, fees, balance sheet, collateral, reporting lag and execution availability.
- **Acceptance:** SPEC AC-001..AC-005 must have deterministic fixtures, test names and independent reviewer signoff.
- **Negative-result rule:** publish a failed or inconclusive hypothesis with exact limitations rather than optimizing the story after the fact.
**No calculated results or confidence bounds are claimed.**
