# EVALS — Balance-Sheet Seasonality Arbitrage
**Not yet run.**
- **Hypothesis:** Calendar-aware funding reduces ex-ante cost on unseen quarter-ends after realistic balance-sheet charges.
- **Comparator:** constant overnight-roll financing.
- **Candidate:** calendar event study with capacity-aware optimization; later assess stochastic dynamic capacity control under regime variation.
- **Economic metrics:** holdout funding cost, stress liquidity, rollover risk and drawdown.
- **Falsification:** reject the candidate if it fails to deliver economically material improvement against baseline after full costs, legal constraints, risk limits and multiple-testing checks.
- **Time safety:** use source `available_at` <= decision clock, embargo for overlapping forward outcomes, preserve revisions, avoid survivor selection.
- **Stress:** well-known quarter-end effects may already be fully priced.
- **Robustness:** resample market events with appropriate block bootstrap, vary spreads, fees, balance sheet, collateral, reporting lag and execution availability.
- **Acceptance:** SPEC AC-001..AC-005 must have deterministic fixtures, test names and independent reviewer signoff.
- **Negative-result rule:** publish a failed or inconclusive hypothesis with exact limitations rather than optimizing the story after the fact.
**No calculated results or confidence bounds are claimed.**
