---
name: triparty-eligibility-compiler
description: "Evaluate Tri-Party Collateral Eligibility Clause-to-Constraint Compiler with a time-vintaged baseline, feasibility constraints and economic falsification."
---
# SKILL — Tri-Party Collateral Eligibility Clause-to-Constraint Compiler
## Trigger
Use this skill when researching: **Compile approved eligibility schedules into testable constraints before collateral allocation, with human adjudication of ambiguous clauses.** in **US triparty and secured funding**.

## Inputs
Source/version references and license, decision clock, contract clause × effective version × collateral asset × valuation time, the cost model, allowed actions, and study windows. Minimum fields: Synthetic collateral schedules; asset master; rating/issuer; eligibility categories; haircut tables; human-labeled clause examples..

## Procedure
1. Load SPEC and HANDOFF; state hypothesis and category A · Securities finance.
2. Build source-claim ledger. Do not conflate official data description and available executable market dataset.
3. Check first public availability and carry correction vintages forward, never backward.
4. Create adverse synthetic fixtures and reject invalid market constraints.
5. Fit and run **Rule tables hand-transcribed and checked by two human operators.** on training data with full costs.
6. Define **Schema-constrained text extraction with symbolic eligibility evaluation and abstention.**, plus optional **Contradiction-aware graph of rule amendments with formal test generation and reviewer feedback.** conditional on simple model advantage.
7. Freeze chronological holdouts and evaluate **false eligibility acceptance rate, false rejection rate, review labor, coverage, abstention, parse latency.** plus capacity and tail risk.
8. Try to falsify: **Reject if any critical false acceptance appears in stress fixtures or human review burden fails to improve.**.
9. Record all negative tests, unverified sources, measured trade-offs and manual approval gate.
10. Return BLOCKED if Natural-language ambiguity, contract precedence and jurisdiction-specific clauses make full automation unsafe. cannot be mitigated.

## Artifacts and failure behavior
Future proposed artifacts: `run_manifest.json`, `source_claim_ledger.md`, `costed_baseline.json`, `paired_evaluation.json`, `human_review.md`.
None are presently created by this design. Never report historical profits, tests passed or production promotion without evidence.
