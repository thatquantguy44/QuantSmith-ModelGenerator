# TOOLING — Asia–US Cross-Listed ADR Opening Auction Information Transfer
## Proposed Python stack — not installed or executed
`numpy, statsmodels, polars, scipy`. Pin versions with `uv.lock`/hash constraints at implementation; no specific versions asserted as tested.

## Reusable interface architecture
`qmg_core.sources.SourceLicense` — public/vendor/private classification and original publication snapshots.
`qmg_core.point_in_time.asof_join()` — enforce `available_at_utc <= decision_at_utc`.
`qmg_core.calendar.tradable_next_session()` — regional trade/auction calendars.
`qmg_core.economics.CounterfactualCost` — explicit transaction, funding, liquidity, capital and operational charges.
`qmg_core.evals.paired_walk_forward()` — frozen counterfactual opportunities and confidence bands.
`qmg_core.claims.EvidenceLedger` — sourced facts separated from hypotheses.

## Idea-specific modules (proposals)
`src/qmg/research/asia_us_adr_opening_price_discovery/contracts.py`, `adapters.py`, `baseline.py`, `candidate.py`, `constraints.py`, `eval.py`, `cli.py`.
- `baseline.py`: Last home close × publicly known ADR conversion ratio × contemporaneous FX spot
- `candidate.py`: State-space asynchronous Kalman fair-value update using futures and related peer prices
- `constraints.py`: Ratio_i is point-in-time ADR share ratio, FX has correct currency direction, CrossMarketNews is post-local close information known before US auction.
- `eval.py`: auction fair-value error, paired realized slippage, inventory risk, settlement/convertibility feasibility
**Primary bottleneck:** ADR conversion fees, access restrictions, local holidays and stale home quotes create phantom arbitrage.

## Tooling governance
No LLM-controlled order execution, no hardcoded credentials, no licensed payloads stored here. Capability declarations are plans, **not deployed agents or working CLIs**.
