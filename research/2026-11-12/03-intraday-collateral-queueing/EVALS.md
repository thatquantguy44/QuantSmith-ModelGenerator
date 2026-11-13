# EVALS — Intraday Collateral Liquidity Forecasting via Queueing Theory
**Not yet run.**
- **Hypothesis:** Queue-aware controls lower buffer expense without increasing missed margin deadlines.
- **Comparator:** fixed intraday liquidity reserve.
- **Candidate:** stochastic queueing and priority model; later assess model predictive control with chance-constrained service levels.
- **Economic metrics:** liquidity buffer cost, p99 delay, shortfalls and failures.
- **Falsification:** reject the candidate if it fails to deliver economically material improvement against baseline after full costs, legal constraints, risk limits and multiple-testing checks.
- **Time safety:** use source `available_at` <= decision clock, embargo for overlapping forward outcomes, preserve revisions, avoid survivor selection.
- **Stress:** timestamp quality and hidden queue-priority rules.
- **Robustness:** resample market events with appropriate block bootstrap, vary spreads, fees, balance sheet, collateral, reporting lag and execution availability.
- **Acceptance:** SPEC AC-001..AC-005 must have deterministic fixtures, test names and independent reviewer signoff.
- **Negative-result rule:** publish a failed or inconclusive hypothesis with exact limitations rather than optimizing the story after the fact.
**No calculated results or confidence bounds are claimed.**
