---
name: lending-fee-selection-debiasing
description: "Evaluate Securities-Lending Fee Observability & Selection-Bias Corrector with a time-vintaged baseline, feasibility constraints and economic falsification."
---
# SKILL — Securities-Lending Fee Observability & Selection-Bias Corrector
## Trigger
Use this skill when researching: **Publish uncertainty-aware fee benchmarks and abstain from quote-setting when selected sample coverage is inadequate.** in **US/global securities lending benchmarks**.

## Inputs
Source/version references and license, decision clock, security × lending day × vendor/contributor population, the cost model, allowed actions, and study windows. Minimum fields: Contributed executed fee samples; public security volume/short-interest proxies; locate response metadata; source coverage and revisions..

## Procedure
1. Load SPEC and HANDOFF; state hypothesis and category A · Securities finance.
2. Build source-claim ledger. Do not conflate official data description and available executable market dataset.
3. Check first public availability and carry correction vintages forward, never backward.
4. Create adverse synthetic fixtures and reject invalid market constraints.
5. Fit and run **Daily equally weighted or outstanding-value-weighted observed market fees.** on training data with full costs.
6. Define **Doubly robust weighting with overlap and selection-sensitivity intervals.**, plus optional **Bayesian selection model with unverifiable missing-not-at-random stress bounds.** conditional on simple model advantage.
7. Freeze chronological holdouts and evaluate **cross-contributor benchmark error, interval coverage, abstention, quote drift, market breadth coverage.** plus capacity and tail risk.
8. Try to falsify: **Reject if cross-contributor MAE reduction <10% or intervals under-cover known withheld contributions.**.
9. Record all negative tests, unverified sources, measured trade-offs and manual approval gate.
10. Return BLOCKED if Missing-not-at-random selection cannot be identified from executed loans alone; confidence intervals can be falsely narrow. cannot be mitigated.

## Artifacts and failure behavior
Future proposed artifacts: `run_manifest.json`, `source_claim_ledger.md`, `costed_baseline.json`, `paired_evaluation.json`, `human_review.md`.
None are presently created by this design. Never report historical profits, tests passed or production promotion without evidence.
