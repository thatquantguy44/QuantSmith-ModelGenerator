# TOOLING — Canadian Mortgage Renewal Cohorts to Bank Credit-Risk Dispersion
## Proposed Python stack — not installed or executed
`numpy, pandas, pymc, statsmodels`. Pin versions with `uv.lock`/hash constraints at implementation; no specific versions asserted as tested.

## Reusable interface architecture
`qmg_core.sources.SourceLicense` — public/vendor/private classification and original publication snapshots.
`qmg_core.point_in_time.asof_join()` — enforce `available_at_utc <= decision_at_utc`.
`qmg_core.calendar.tradable_next_session()` — regional trade/auction calendars.
`qmg_core.economics.CounterfactualCost` — explicit transaction, funding, liquidity, capital and operational charges.
`qmg_core.evals.paired_walk_forward()` — frozen counterfactual opportunities and confidence bands.
`qmg_core.claims.EvidenceLedger` — sourced facts separated from hypotheses.

## Idea-specific modules (proposals)
`src/qmg/research/canadian_mortgage_renewal_bank_risk/contracts.py`, `adapters.py`, `baseline.py`, `candidate.py`, `constraints.py`, `eval.py`, `cli.py`.
- `baseline.py`: Bank loss sensitivity to national unemployment and policy rate alone
- `candidate.py`: Vintage-cohort mortgage reset microsimulation from public aggregates
- `constraints.py`: Balance is refinanceable exposure (public aggregate proxy initially), ECL expected credit loss; individual bank vintage mapping may be incomplete.
- `eval.py`: future loss forecast gain, bank-spread risk hedging, sensitivity to vintage assumptions, net hedging cost
**Primary bottleneck:** Public aggregate cohorts do not identify each bank's borrower vintage distribution or underwriting quality.

## Tooling governance
No LLM-controlled order execution, no hardcoded credentials, no licensed payloads stored here. Capability declarations are plans, **not deployed agents or working CLIs**.
