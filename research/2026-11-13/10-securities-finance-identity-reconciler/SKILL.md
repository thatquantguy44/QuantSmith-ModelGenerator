---
name: securities-finance-identity-reconciler
description: "Evaluate Cross-Book Securities Finance Identity Reconciliation Graph with a time-vintaged baseline, feasibility constraints and economic falsification."
---
# SKILL — Cross-Book Securities Finance Identity Reconciliation Graph
## Trigger
Use this skill when researching: **Resolve and quarantine inconsistent identities before financing position, collateral and exposure optimization.** in **US and cross-border securities-finance operations**.

## Inputs
Source/version references and license, decision clock, source record × canonical candidate × event version × timestamp, the cost model, allowed actions, and study windows. Minimum fields: Synthetic records containing lifecycle events, ISIN/CUSIP, product type, settlement date, amount, counterparty alias and amendment chain..

## Procedure
1. Load SPEC and HANDOFF; state hypothesis and category A · Securities finance.
2. Build source-claim ledger. Do not conflate official data description and available executable market dataset.
3. Check first public availability and carry correction vintages forward, never backward.
4. Create adverse synthetic fixtures and reject invalid market constraints.
5. Fit and run **Exact ID join plus manually triaged fuzzy-name matches.** on training data with full costs.
6. Define **Bipartite deterministic matching with hard identity constraints and provenance.**, plus optional **Human-review active-learning on uncertain clusters with error budget and privacy-preserving synthetic tests.** conditional on simple model advantage.
7. Freeze chronological holdouts and evaluate **false merge rate, unmatched %, time to resolve, duplicate exposure USD, manual review hours.** plus capacity and tail risk.
8. Try to falsify: **Reject if critical false merges exceed zero in labeled holdouts or operations time does not decline.**.
9. Record all negative tests, unverified sources, measured trade-offs and manual approval gate.
10. Return BLOCKED if LLM or probabilistic model can silently merge legally distinct entities or settlement legs. cannot be mitigated.

## Artifacts and failure behavior
Future proposed artifacts: `run_manifest.json`, `source_claim_ledger.md`, `costed_baseline.json`, `paired_evaluation.json`, `human_review.md`.
None are presently created by this design. Never report historical profits, tests passed or production promotion without evidence.
