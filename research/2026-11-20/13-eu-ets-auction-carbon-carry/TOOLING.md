# TOOLING — EU ETS Auction Supply Revision and Carbon Futures Carry
## Proposed Python stack — not installed or executed
`statsmodels, cvxpy, pandas, scipy`. Pin versions with `uv.lock`/hash constraints at implementation; no specific versions asserted as tested.

## Reusable interface architecture
`qmg_core.sources.SourceLicense` — public/vendor/private classification and original publication snapshots.
`qmg_core.point_in_time.asof_join()` — enforce `available_at_utc <= decision_at_utc`.
`qmg_core.calendar.tradable_next_session()` — regional trade/auction calendars.
`qmg_core.economics.CounterfactualCost` — explicit transaction, funding, liquidity, capital and operational charges.
`qmg_core.evals.paired_walk_forward()` — frozen counterfactual opportunities and confidence bands.
`qmg_core.claims.EvidenceLedger` — sourced facts separated from hypotheses.

## Idea-specific modules (proposals)
`src/qmg/research/eu_ets_auction_carbon_carry/contracts.py`, `adapters.py`, `baseline.py`, `candidate.py`, `constraints.py`, `eval.py`, `cli.py`.
- `baseline.py`: Calendar-month fixed seasonal allowance spread
- `candidate.py`: Event study of auction schedule revisions and futures risk factors
- `constraints.py`: m,n are contract maturities; expectations only use public revisions available before trade, not full-year realized auction volumes.
- `eval.py`: EUA spread basis MAE, hedged risk reduction, net carry after fees, low-liquidity scenario loss
**Primary bottleneck:** Policy revision expectations may be priced before official publication; futures/Registry coverage not contemporaneous.

## Tooling governance
No LLM-controlled order execution, no hardcoded credentials, no licensed payloads stored here. Capability declarations are plans, **not deployed agents or working CLIs**.
