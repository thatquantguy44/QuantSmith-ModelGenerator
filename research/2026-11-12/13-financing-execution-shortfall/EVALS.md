# EVALS — Financing Execution Shortfall Model
**Not yet run.**
- **Hypothesis:** Point-in-time causal leakage attribution discovers correctable costs over a quote-only baseline.
- **Comparator:** executed spread minus indicative quote.
- **Candidate:** cost-inclusive execution shortfall event ledger; later assess matched counterfactual execution-policy evaluator.
- **Economic metrics:** bps slippage, recovered P&L, latency and fill rate.
- **Falsification:** reject the candidate if it fails to deliver economically material improvement against baseline after full costs, legal constraints, risk limits and multiple-testing checks.
- **Time safety:** use source `available_at` <= decision clock, embargo for overlapping forward outcomes, preserve revisions, avoid survivor selection.
- **Stress:** quotes may be non-executable; client selection creates bias.
- **Robustness:** resample market events with appropriate block bootstrap, vary spreads, fees, balance sheet, collateral, reporting lag and execution availability.
- **Acceptance:** SPEC AC-001..AC-005 must have deterministic fixtures, test names and independent reviewer signoff.
- **Negative-result rule:** publish a failed or inconclusive hypothesis with exact limitations rather than optimizing the story after the fact.
**No calculated results or confidence bounds are claimed.**
