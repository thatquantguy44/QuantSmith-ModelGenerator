# EVALS — Collateral Reuse Chain Stress Testing
**Not yet run.**
- **Hypothesis:** Provenance-aware reuse graph explains stress contractions beyond gross reused collateral.
- **Comparator:** gross collateral stock and static stress.
- **Candidate:** legal reuse network input-output simulation; later assess dynamic network cascades with haircuts and intraday liquidity.
- **Economic metrics:** capacity contraction, margin calls, recovery time and chain failure.
- **Falsification:** reject the candidate if it fails to deliver economically material improvement against baseline after full costs, legal constraints, risk limits and multiple-testing checks.
- **Time safety:** use source `available_at` <= decision clock, embargo for overlapping forward outcomes, preserve revisions, avoid survivor selection.
- **Stress:** double counting and unsupported rehypothecation rights.
- **Robustness:** resample market events with appropriate block bootstrap, vary spreads, fees, balance sheet, collateral, reporting lag and execution availability.
- **Acceptance:** SPEC AC-001..AC-005 must have deterministic fixtures, test names and independent reviewer signoff.
- **Negative-result rule:** publish a failed or inconclusive hypothesis with exact limitations rather than optimizing the story after the fact.
**No calculated results or confidence bounds are claimed.**
