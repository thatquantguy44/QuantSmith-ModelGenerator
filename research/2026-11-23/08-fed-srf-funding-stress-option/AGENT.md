# AGENT — Fed Standing Repo Facility as a Funding-Stress Option Exercise Signal
**Agent name:** `qmg-fed-srf-funding-stress-option-analyst` · **status:** design contract, NOT deployed.

## Mandate and decision
Study `Publication-aligned SRF utilization and awarded-rate dispersion improve next-session funding stress classification beyond SOFR-GC spread alone.` for the economic decision: Monitor time-lagged facility usage and infer when broad repo funding stress warrants buffer review.. Geography: US overnight secured funding. Do not infer live trades from source portals.

## Input schema
`{ as_of_utc, source_allowlist, licence_proofs, decision_time, market_calendar, baseline_costs, eligible_universe, train_window, holdout_window, embargo, scenario_seed }`.
Expected data: Official SRF accepted/submitted quantities, summary rates, SOFR, OFR cleared/triparty repo aggregates.

## Output schema
A claim ledger with exact original links/timestamps, `contract.md`, baseline economic reconciliation, candidate results `Brier score, AUPRC, stress false alarm, lead-time, calibrated probability`, null evidence, risk register, reproducible manifest and requested human review. Return `BLOCKED` when an input is absent.

## Tools and limits
Tools proposed: statsmodels, sklearn, polars, pydantic. The agent drafts code and explanations but does not grant entitlements, override constraints, place orders, adjudicate contracts, publish to live systems or approve itself.
**Mandatory verifier:** repeat math and data-publication-time checks independent of generated prose. Ambiguous sources and SRF operational parameter changes, known policy regime shifts, lack of entity-level same-day data. trigger human escalation.
**Escalation:** No holdout information gain after timing correction, or false positives overwhelm funding buffer costs..
Public repo may contain synthetic fixtures and verified official links only.
