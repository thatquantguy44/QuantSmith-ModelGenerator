---
name: us-euro-curve-release-shocks
description: "Evaluate US–Euro Sovereign Curve Shock Decomposition with Data Vintages with a time-vintaged baseline, feasibility constraints and economic falsification."
---
# SKILL — US–Euro Sovereign Curve Shock Decomposition with Data Vintages
## Trigger
Use this skill when researching: **Allocate DV01-neutral rates hedge exposure between US and European curve tenors after releases, subject to actual market liquidity.** in **United States and euro area**.

## Inputs
Source/version references and license, decision clock, economic release event × curve tenor × publication instant × geography, the cost model, allowed actions, and study windows. Minimum fields: ECB published euro yield curve, US yields and ALFRED macro vintages, official release times, FX hedges, rates futures cost..

## Procedure
1. Load SPEC and HANDOFF; state hypothesis and category B · Domestic & global markets.
2. Build source-claim ledger. Do not conflate official data description and available executable market dataset.
3. Check first public availability and carry correction vintages forward, never backward.
4. Create adverse synthetic fixtures and reject invalid market constraints.
5. Fit and run **60-day rolling DV01-neutral cross-market beta hedge.** on training data with full costs.
6. Define **Vintaged announcement factor model plus shrinkage hedge weights.**, plus optional **Hierarchical structural yield-curve state-space with distinct real-rate and term-premium factor loading.** conditional on simple model advantage.
7. Freeze chronological holdouts and evaluate **OOS hedging variance reduction, implementation shortfall, tail DV01 loss, signal turnover.** plus capacity and tail risk.
8. Try to falsify: **Reject if hedge variance does not improve at least 5% net of turnover on independent event holdout.**.
9. Record all negative tests, unverified sources, measured trade-offs and manual approval gate.
10. Return BLOCKED if Public releases cannot recreate market consensus surprises without a licensed historical consensus dataset or explicit no-consensus baseline. cannot be mitigated.

## Artifacts and failure behavior
Future proposed artifacts: `run_manifest.json`, `source_claim_ledger.md`, `costed_baseline.json`, `paired_evaluation.json`, `human_review.md`.
None are presently created by this design. Never report historical profits, tests passed or production promotion without evidence.
