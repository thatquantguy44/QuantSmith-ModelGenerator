# EVALS — Cross-Currency Repo Basis Optimization
**Not yet run.**
- **Hypothesis:** CIP-adjusted multi-currency routing beats domestic-only financing where transferable collateral exists.
- **Comparator:** domestic collateral and repo only.
- **Candidate:** covered-interest-parity-adjusted funding network; later assess stochastic multi-currency funding and collateral flow.
- **Economic metrics:** hedged carry, capacity, FX basis risk and all-in spread.
- **Falsification:** reject the candidate if it fails to deliver economically material improvement against baseline after full costs, legal constraints, risk limits and multiple-testing checks.
- **Time safety:** use source `available_at` <= decision clock, embargo for overlapping forward outcomes, preserve revisions, avoid survivor selection.
- **Stress:** false arbitrage from stale asynchronous or inaccessible quotes.
- **Robustness:** resample market events with appropriate block bootstrap, vary spreads, fees, balance sheet, collateral, reporting lag and execution availability.
- **Acceptance:** SPEC AC-001..AC-005 must have deterministic fixtures, test names and independent reviewer signoff.
- **Negative-result rule:** publish a failed or inconclusive hypothesis with exact limitations rather than optimizing the story after the fact.
**No calculated results or confidence bounds are claimed.**
