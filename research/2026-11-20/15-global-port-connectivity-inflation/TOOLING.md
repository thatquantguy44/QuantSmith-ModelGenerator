# TOOLING — Global Shipping Connectivity Re-Routing to Inflation and Equity Margins
## Proposed Python stack — not installed or executed
`networkx, statsmodels, numpy, geopandas`. Pin versions with `uv.lock`/hash constraints at implementation; no specific versions asserted as tested.

## Reusable interface architecture
`qmg_core.sources.SourceLicense` — public/vendor/private classification and original publication snapshots.
`qmg_core.point_in_time.asof_join()` — enforce `available_at_utc <= decision_at_utc`.
`qmg_core.calendar.tradable_next_session()` — regional trade/auction calendars.
`qmg_core.economics.CounterfactualCost` — explicit transaction, funding, liquidity, capital and operational charges.
`qmg_core.evals.paired_walk_forward()` — frozen counterfactual opportunities and confidence bands.
`qmg_core.claims.EvidenceLedger` — sourced facts separated from hypotheses.

## Idea-specific modules (proposals)
`src/qmg/research/global_port_connectivity_inflation/contracts.py`, `adapters.py`, `baseline.py`, `candidate.py`, `constraints.py`, `eval.py`, `cli.py`.
- `baseline.py`: Aggregate global shipping index versus region CPI with fixed lag
- `candidate.py`: Supply-route network exposure local projections
- `constraints.py`: r is importer region, p port corridor; shocks and alternate route count must use actually published index vintage.
- `eval.py`: inflation nowcast gain, equity margin dispersion, attribution stability and hedged net P&L
**Primary bottleneck:** Connectivity is not real-time port congestion and quarterly updates can obscure freight cycle timing.

## Tooling governance
No LLM-controlled order execution, no hardcoded credentials, no licensed payloads stored here. Capability declarations are plans, **not deployed agents or working CLIs**.
