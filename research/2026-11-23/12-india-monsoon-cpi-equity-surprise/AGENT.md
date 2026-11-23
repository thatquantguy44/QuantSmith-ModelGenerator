# AGENT — India Monsoon Surprise to Food CPI and Local Equity Pricing
**Agent name:** `qmg-india-monsoon-cpi-equity-surprise-analyst` · **status:** design contract, NOT deployed.

## Mandate and decision
Study `Rainfall surprises weighted by district crop patterns predict food-CPI subcomponents and cross-sectional consumer equity earnings revisions beyond national rainfall.` for the economic decision: Time/hedge exposures to monsoon-sensitive consumption and agriculture pricing after publicly available rainfall surprises.. Geography: India, state agriculture, INR and Indian listed consumer equities. Do not infer live trades from source portals.

## Input schema
`{ as_of_utc, source_allowlist, licence_proofs, decision_time, market_calendar, baseline_costs, eligible_universe, train_window, holdout_window, embargo, scenario_seed }`.
Expected data: IMD daily district rain, crop sowing weights, RBI CPI release, state-level harvest, NSE sector returns.

## Output schema
A claim ledger with exact original links/timestamps, `contract.md`, baseline economic reconciliation, candidate results `CPI MAE, sector neutral-return IC, hit rate net costs, seasonal robustness`, null evidence, risk register, reproducible manifest and requested human review. Return `BLOCKED` when an input is absent.

## Tools and limits
Tools proposed: xarray, geopandas, pymc, statsmodels. The agent drafts code and explanations but does not grant entitlements, override constraints, place orders, adjudicate contracts, publish to live systems or approve itself.
**Mandatory verifier:** repeat math and data-publication-time checks independent of generated prose. Ambiguous sources and Historical IMD OGD resources lag, crop mix revisions, rainfall not yield and policy interventions. trigger human escalation.
**Escalation:** No incremental holdout inflation forecast or stock-return effect against rainfall benchmark..
Public repo may contain synthetic fixtures and verified official links only.
