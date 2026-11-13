# EVALS — Securities Lending Liquidity Provision Premium
**Not yet run.**
- **Hypothesis:** Stress supply resilience predicts financing yield beyond security composition and usage.
- **Comparator:** trailing revenue per lendable dollar.
- **Candidate:** conditional financing factor decomposition; later assess endogenous supply/fee equilibrium with nonlinear downside beta.
- **Economic metrics:** stress carry, stability, adjusted yield and mandate value.
- **Falsification:** reject the candidate if it fails to deliver economically material improvement against baseline after full costs, legal constraints, risk limits and multiple-testing checks.
- **Time safety:** use source `available_at` <= decision clock, embargo for overlapping forward outcomes, preserve revisions, avoid survivor selection.
- **Stress:** composition and survivorship bias can masquerade as a premium.
- **Robustness:** resample market events with appropriate block bootstrap, vary spreads, fees, balance sheet, collateral, reporting lag and execution availability.
- **Acceptance:** SPEC AC-001..AC-005 must have deterministic fixtures, test names and independent reviewer signoff.
- **Negative-result rule:** publish a failed or inconclusive hypothesis with exact limitations rather than optimizing the story after the fact.
**No calculated results or confidence bounds are claimed.**
