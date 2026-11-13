# EVALS — Auction-Based Securities Lending Liquidity Discovery
**Not yet run.**
- **Hypothesis:** A structural auction policy improves net revenue over highest-fee-first after response and retention costs.
- **Comparator:** highest-fee-first feasible allocation.
- **Candidate:** censored structural demand + constrained auction; later assess hierarchical Bayesian mechanism design.
- **Economic metrics:** net revenue, allocative efficiency, fill rate, churn and regret.
- **Falsification:** reject the candidate if it fails to deliver economically material improvement against baseline after full costs, legal constraints, risk limits and multiple-testing checks.
- **Time safety:** use source `available_at` <= decision clock, embargo for overlapping forward outcomes, preserve revisions, avoid survivor selection.
- **Stress:** censored demand, endogenous quote selection.
- **Robustness:** resample market events with appropriate block bootstrap, vary spreads, fees, balance sheet, collateral, reporting lag and execution availability.
- **Acceptance:** SPEC AC-001..AC-005 must have deterministic fixtures, test names and independent reviewer signoff.
- **Negative-result rule:** publish a failed or inconclusive hypothesis with exact limitations rather than optimizing the story after the fact.
**No calculated results or confidence bounds are claimed.**
