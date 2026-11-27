# AGENT — US Bank Deposit Beta and Mark-to-Market Securities Run Risk
**Agent name:** `qmg-us-bank-deposit-beta-run-risk-analyst` · **status:** design contract, NOT deployed.

## Mandate and decision
Study `A joint deposit-beta and securities mark-to-market gap predicts earnings/credit deterioration better than uninsured deposit percentage.` for the economic decision: Assess which banks face funding-cost and securities-loss convexity under uninsured deposit migration.. Geography: US regional banks and bank-sector equity/credit. Do not infer live trades from source portals.

## Input schema
`{ as_of_utc, source_allowlist, licence_proofs, decision_time, market_calendar, baseline_costs, eligible_universe, train_window, holdout_window, embargo, scenario_seed }`.
Expected data: FDIC bank Call Reports, quarterly uninsured deposits, HTM/AFS loss fields, benchmark rates, bank equity CDS.

## Output schema
A claim ledger with exact original links/timestamps, `contract.md`, baseline economic reconciliation, candidate results `Next-quarter NII loss, downside rank precision, capital shortfall, sector-neutral return IC`, null evidence, risk register, reproducible manifest and requested human review. Return `BLOCKED` when an input is absent.

## Tools and limits
Tools proposed: statsmodels, polars, pymc, duckdb. The agent drafts code and explanations but does not grant entitlements, override constraints, place orders, adjudicate contracts, publish to live systems or approve itself.
**Mandatory verifier:** repeat math and data-publication-time checks independent of generated prose. Ambiguous sources and Quarterly revisions, mergers, bank survivorship and missing bank-specific deposit pricing. trigger human escalation.
**Escalation:** No incremental forecast versus capital/deposit mix baseline after strict public release lag..
Public repo may contain synthetic fixtures and verified official links only.
