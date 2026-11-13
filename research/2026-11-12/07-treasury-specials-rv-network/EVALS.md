# EVALS — Treasury Specials Relative-Value Network
**Not yet run.**
- **Hypothesis:** A supply-aware graph explains and monetizes relative scarcity after full trading costs.
- **Comparator:** historical CUSIP z-score of specials.
- **Candidate:** CUSIP graph, cointegration and structural event controls; later assess dynamic security-specific financing equilibrium.
- **Economic metrics:** net spread convergence, realized returns, capital and fail risk.
- **Falsification:** reject the candidate if it fails to deliver economically material improvement against baseline after full costs, legal constraints, risk limits and multiple-testing checks.
- **Time safety:** use source `available_at` <= decision clock, embargo for overlapping forward outcomes, preserve revisions, avoid survivor selection.
- **Stress:** public SOMA cannot substitute for executable CUSIP quotes.
- **Robustness:** resample market events with appropriate block bootstrap, vary spreads, fees, balance sheet, collateral, reporting lag and execution availability.
- **Acceptance:** SPEC AC-001..AC-005 must have deterministic fixtures, test names and independent reviewer signoff.
- **Negative-result rule:** publish a failed or inconclusive hypothesis with exact limitations rather than optimizing the story after the fact.
**No calculated results or confidence bounds are claimed.**
