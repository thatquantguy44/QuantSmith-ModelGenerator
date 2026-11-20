# TOOLING — Korean Household Debt-Service Shock to Bank–Consumer Equity Spread
## Proposed Python stack — not installed or executed
`linearmodels, statsmodels, pyarrow, cvxpy`. Pin versions with `uv.lock`/hash constraints at implementation; no specific versions asserted as tested.

## Reusable interface architecture
`qmg_core.sources.SourceLicense` — public/vendor/private classification and original publication snapshots.
`qmg_core.point_in_time.asof_join()` — enforce `available_at_utc <= decision_at_utc`.
`qmg_core.calendar.tradable_next_session()` — regional trade/auction calendars.
`qmg_core.economics.CounterfactualCost` — explicit transaction, funding, liquidity, capital and operational charges.
`qmg_core.evals.paired_walk_forward()` — frozen counterfactual opportunities and confidence bands.
`qmg_core.claims.EvidenceLedger` — sourced facts separated from hypotheses.

## Idea-specific modules (proposals)
`src/qmg/research/korea_household_debt_equity_dispersion/contracts.py`, `adapters.py`, `baseline.py`, `candidate.py`, `constraints.py`, `eval.py`, `cli.py`.
- `baseline.py`: Equal-beta long banks short consumer discretionary with lagged policy-rate signal
- `candidate.py`: Panel local projections with shrinkage and sector time fixed effects
- `constraints.py`: b bank peer basket, c consumer peer basket, h disclosure-to-outcome window; DSRSurprise uses real-time expected vs published DSR, not revised future panels.
- `eval.py`: cross-sector earnings forecast delta, beta-neutral IR, worst-regime drawdown, capacity after local spreads
**Primary bottleneck:** Endogenous rate policy and sector composition cause confounding; public issuer histories need delisting continuity.

## Tooling governance
No LLM-controlled order execution, no hardcoded credentials, no licensed payloads stored here. Capability declarations are plans, **not deployed agents or working CLIs**.
