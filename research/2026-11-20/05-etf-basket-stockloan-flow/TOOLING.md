# TOOLING — ETF Creation/Redemption Basket Shock to Stock-Loan Supply
## Proposed Python stack — not installed or executed
`polars, statsmodels, linearmodels, scipy`. Pin versions with `uv.lock`/hash constraints at implementation; no specific versions asserted as tested.

## Reusable interface architecture
`qmg_core.sources.SourceLicense` — public/vendor/private classification and original publication snapshots.
`qmg_core.point_in_time.asof_join()` — enforce `available_at_utc <= decision_at_utc`.
`qmg_core.calendar.tradable_next_session()` — regional trade/auction calendars.
`qmg_core.economics.CounterfactualCost` — explicit transaction, funding, liquidity, capital and operational charges.
`qmg_core.evals.paired_walk_forward()` — frozen counterfactual opportunities and confidence bands.
`qmg_core.claims.EvidenceLedger` — sourced facts separated from hypotheses.

## Idea-specific modules (proposals)
`src/qmg/research/etf_basket_stockloan_flow/contracts.py`, `adapters.py`, `baseline.py`, `candidate.py`, `constraints.py`, `eval.py`, `cli.py`.
- `baseline.py`: Change in ETF shares outstanding plus index-event dummy
- `candidate.py`: Hierarchical event study with issuer-basket aggregation and controls
- `constraints.py`: i is CUSIP, h forecast horizon, basket delta is an appropriately signed and actually available in-kind constituent-flow measure; no lookahead custom basket files.
- `eval.py`: inventory forecast MAE, short availability calibration, incremental net inventory carry, execution slippage
**Primary bottleneck:** Most executable AP basket details and actual stock-loan supply are not public.

## Tooling governance
No LLM-controlled order execution, no hardcoded credentials, no licensed payloads stored here. Capability declarations are plans, **not deployed agents or working CLIs**.
