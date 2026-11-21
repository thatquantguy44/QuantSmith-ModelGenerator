# TOOLING — Japan FX Intervention Impact and Option-Skew Persistence
## Proposed Python stack — not installed or executed
`statsmodels, linearmodels, arch, scipy`. Pin versions with `uv.lock`/hash constraints at implementation; no specific versions asserted as tested.

## Reusable interface architecture
`qmg_core.sources.SourceLicense` — public/vendor/private classification and original publication snapshots.
`qmg_core.point_in_time.asof_join()` — enforce `available_at_utc <= decision_at_utc`.
`qmg_core.calendar.tradable_next_session()` — regional trade/auction calendars.
`qmg_core.economics.CounterfactualCost` — explicit transaction, funding, liquidity, capital and operational charges.
`qmg_core.evals.paired_walk_forward()` — frozen counterfactual opportunities and confidence bands.
`qmg_core.claims.EvidenceLedger` — sourced facts separated from hypotheses.

## Idea-specific modules (proposals)
`src/qmg/research/japan_fx_intervention_persistence/contracts.py`, `adapters.py`, `baseline.py`, `candidate.py`, `constraints.py`, `eval.py`, `cli.py`.
- `baseline.py`: Standard spot momentum and monetary-policy announcement dummy
- `candidate.py`: Disclosure-timestamp event study with matched controls and local projections
- `constraints.py`: InterventionKnownAt_t is zero until event is publicly known or release issued; h is forward horizon, and skew is an executable options quote measure.
- `eval.py`: incremental forward skew/vol forecast skill, delta-hedged net P&L, placebo events, risk-adjusted drawdown
**Primary bottleneck:** Actual intervention execution is not transparently known in real time; small event count undermines causal certainty.

## Tooling governance
No LLM-controlled order execution, no hardcoded credentials, no licensed payloads stored here. Capability declarations are plans, **not deployed agents or working CLIs**.
