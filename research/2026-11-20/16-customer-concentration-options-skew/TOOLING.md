# TOOLING — Issuer Customer-Concentration Disclosure to Earnings Options Skew
## Proposed Python stack — not installed or executed
`sec-edgar-downloader, statsmodels, scipy, pandas`. Pin versions with `uv.lock`/hash constraints at implementation; no specific versions asserted as tested.

## Reusable interface architecture
`qmg_core.sources.SourceLicense` — public/vendor/private classification and original publication snapshots.
`qmg_core.point_in_time.asof_join()` — enforce `available_at_utc <= decision_at_utc`.
`qmg_core.calendar.tradable_next_session()` — regional trade/auction calendars.
`qmg_core.economics.CounterfactualCost` — explicit transaction, funding, liquidity, capital and operational charges.
`qmg_core.evals.paired_walk_forward()` — frozen counterfactual opportunities and confidence bands.
`qmg_core.claims.EvidenceLedger` — sourced facts separated from hypotheses.

## Idea-specific modules (proposals)
`src/qmg/research/customer_concentration_options_skew/contracts.py`, `adapters.py`, `baseline.py`, `candidate.py`, `constraints.py`, `eval.py`, `cli.py`.
- `baseline.py`: Size/leverage/industry/earnings event-only option skew estimator
- `candidate.py`: Censored-disclosure panel with inverse observation probability adjustment
- `constraints.py`: HHI is sum of squared disclosed customer revenue shares (bounded/partially observed); t-known is filing dissemination time, not fiscal year end.
- `eval.py`: post-filing skew residual, risk hedge efficiency, delta-neutral net performance and disclosure coverage
**Primary bottleneck:** Customer concentrations may be anonymized and nonrandomly omitted; options trade data can be illiquid.

## Tooling governance
No LLM-controlled order execution, no hardcoded credentials, no licensed payloads stored here. Capability declarations are plans, **not deployed agents or working CLIs**.
