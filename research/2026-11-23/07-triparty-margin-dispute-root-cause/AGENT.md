# AGENT — Tri-Party Repo Margin Dispute Root-Cause and Evidence Classifier
**Agent name:** `qmg-triparty-margin-dispute-root-cause-analyst` · **status:** design contract, NOT deployed.

## Mandate and decision
Study `A deterministic calculation engine plus provenance graph resolves more disputes correctly than keyword-based ticket routing.` for the economic decision: Resolve margin disagreements by independently identifying stale marks, eligibility mismatches and cut-off conventions.. Geography: US and European tri-party collateral. Do not infer live trades from source portals.

## Input schema
`{ as_of_utc, source_allowlist, licence_proofs, decision_time, market_calendar, baseline_costs, eligible_universe, train_window, holdout_window, embargo, scenario_seed }`.
Expected data: Synthetic dispute notices, collateral marks, haircut schedules, legal clocks, status and resolution labels.

## Output schema
A claim ledger with exact original links/timestamps, `contract.md`, baseline economic reconciliation, candidate results `Seeded root-cause accuracy, false escalations, time-to-resolution, unresolved material exposure`, null evidence, risk register, reproducible manifest and requested human review. Return `BLOCKED` when an input is absent.

## Tools and limits
Tools proposed: pydantic, polars, networkx, spaCy, pytest. The agent drafts code and explanations but does not grant entitlements, override constraints, place orders, adjudicate contracts, publish to live systems or approve itself.
**Mandatory verifier:** repeat math and data-publication-time checks independent of generated prose. Ambiguous sources and Conflicting vendor marks, jurisdiction-specific terms, privacy and LLM overconfidence. trigger human escalation.
**Escalation:** LLM cannot improve verified resolver without hallucinated legal clauses or unacceptable false settlements..
Public repo may contain synthetic fixtures and verified official links only.
