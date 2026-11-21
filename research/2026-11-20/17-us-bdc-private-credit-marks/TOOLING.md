# TOOLING — Public BDC Portfolio Fair-Value Markdown Lead Indicator
## Proposed Python stack — not installed or executed
`beautifulsoup4, pandas, pymc, scikit-learn`. Pin versions with `uv.lock`/hash constraints at implementation; no specific versions asserted as tested.

## Reusable interface architecture
`qmg_core.sources.SourceLicense` — public/vendor/private classification and original publication snapshots.
`qmg_core.point_in_time.asof_join()` — enforce `available_at_utc <= decision_at_utc`.
`qmg_core.calendar.tradable_next_session()` — regional trade/auction calendars.
`qmg_core.economics.CounterfactualCost` — explicit transaction, funding, liquidity, capital and operational charges.
`qmg_core.evals.paired_walk_forward()` — frozen counterfactual opportunities and confidence bands.
`qmg_core.claims.EvidenceLedger` — sourced facts separated from hypotheses.

## Idea-specific modules (proposals)
`src/qmg/research/us_bdc_private_credit_marks/contracts.py`, `adapters.py`, `baseline.py`, `candidate.py`, `constraints.py`, `eval.py`, `cli.py`.
- `baseline.py`: BDC aggregate NAV discount and published nonaccrual percentage
- `candidate.py`: Issuer-level mark-hazard panel with censored holdings and missing-not-at-random controls
- `constraints.py`: PriceToCost is reported fair value over cost, nonaccrual flags only as filed, FundLag is filing delay; target is future externally validated credit deterioration.
- `eval.py`: future credit-event AUC/PR, mark-calibration error, NAV stress accuracy, opportunity capacity
**Primary bottleneck:** BDC portfolio company identities, valuation methods and distressed sales are not uniformly disclosed; matching bias.

## Tooling governance
No LLM-controlled order execution, no hardcoded credentials, no licensed payloads stored here. Capability declarations are plans, **not deployed agents or working CLIs**.
