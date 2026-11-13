# EVALS — Repo Term Structure Dislocation Engine
**Not yet run.**
- **Hypothesis:** A collateral-aware funding curve beats overnight rolling after executable financing costs.
- **Comparator:** overnight funding rollover.
- **Candidate:** security-aware no-arbitrage term curve; later assess regime-switching state-space financing optimization.
- **Economic metrics:** after-cost funding savings, basis convergence, risk and drawdown.
- **Falsification:** reject the candidate if it fails to deliver economically material improvement against baseline after full costs, legal constraints, risk limits and multiple-testing checks.
- **Time safety:** use source `available_at` <= decision clock, embargo for overlapping forward outcomes, preserve revisions, avoid survivor selection.
- **Stress:** indicative prices and bid/ask execution mismatch.
- **Robustness:** resample market events with appropriate block bootstrap, vary spreads, fees, balance sheet, collateral, reporting lag and execution availability.
- **Acceptance:** SPEC AC-001..AC-005 must have deterministic fixtures, test names and independent reviewer signoff.
- **Negative-result rule:** publish a failed or inconclusive hypothesis with exact limitations rather than optimizing the story after the fact.
**No calculated results or confidence bounds are claimed.**
