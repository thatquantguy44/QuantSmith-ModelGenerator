# TOOLING — Wheat Export Inspection Revisions to Global Basis and Calendar Spreads
## Proposed Python stack — not installed or executed
`statsmodels, pandas, pymc, scipy`. Pin versions with `uv.lock`/hash constraints at implementation; no specific versions asserted as tested.

## Reusable interface architecture
`qmg_core.sources.SourceLicense` — public/vendor/private classification and original publication snapshots.
`qmg_core.point_in_time.asof_join()` — enforce `available_at_utc <= decision_at_utc`.
`qmg_core.calendar.tradable_next_session()` — regional trade/auction calendars.
`qmg_core.economics.CounterfactualCost` — explicit transaction, funding, liquidity, capital and operational charges.
`qmg_core.evals.paired_walk_forward()` — frozen counterfactual opportunities and confidence bands.
`qmg_core.claims.EvidenceLedger` — sourced facts separated from hypotheses.

## Idea-specific modules (proposals)
`src/qmg/research/global_wheat_export_inspection_basis/contracts.py`, `adapters.py`, `baseline.py`, `candidate.py`, `constraints.py`, `eval.py`, `cli.py`.
- `baseline.py`: Monthly seasonal wheat spread regression using last known WASDE
- `candidate.py`: Mixed-frequency distributed-lag export surprise model
- `constraints.py`: r region; expected inspections estimated using only pre-release history; h is post-release decision horizon with realistic market access.
- `eval.py`: spread forecast delta, regional basis tracking, net slippage-adjusted hedge P&L, regime robustness
**Primary bottleneck:** Weekly inspections differ from actual export commitments; Black Sea supply and policy announcements may dominate.

## Tooling governance
No LLM-controlled order execution, no hardcoded credentials, no licensed payloads stored here. Capability declarations are plans, **not deployed agents or working CLIs**.
