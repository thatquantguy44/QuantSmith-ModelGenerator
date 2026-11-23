# AGENT — Securities Loan Retroactive Rate Amendment Revenue Assurance
**Agent name:** `qmg-stockloan-rate-amendment-auditor-analyst` · **status:** design contract, NOT deployed.

## Mandate and decision
Study `Bitemporal contract-and-loan event reconstruction detects more true billing exceptions than end-of-day price reconciliation without increasing false disputes.` for the economic decision: Identify contractually unsupported retroactive fee amendments before invoice posting.. Geography: Global agent lending / US securities loans. Do not infer live trades from source portals.

## Input schema
`{ as_of_utc, source_allowlist, licence_proofs, decision_time, market_calendar, baseline_costs, eligible_universe, train_window, holdout_window, embargo, scenario_seed }`.
Expected data: Synthetic loans, amendment lifecycle, dated fee notices, loan terminations, currency and day-count conventions.

## Output schema
A claim ledger with exact original links/timestamps, `contract.md`, baseline economic reconciliation, candidate results `Synthetic exception precision/recall, manual hours, invoice basis-point leakage, false escalation rate`, null evidence, risk register, reproducible manifest and requested human review. Return `BLOCKED` when an input is absent.

## Tools and limits
Tools proposed: duckdb, polars, pydantic, hypothesis. The agent drafts code and explanations but does not grant entitlements, override constraints, place orders, adjudicate contracts, publish to live systems or approve itself.
**Mandatory verifier:** repeat math and data-publication-time checks independent of generated prose. Ambiguous sources and Contract-level bilateral waiver rules, fee confirmation ambiguity and out-of-order event feeds. trigger human escalation.
**Escalation:** No improvement in high-severity seeded exceptions relative to deterministic ledger, or unauthorized dispute actions..
Public repo may contain synthetic fixtures and verified official links only.
