---
name: cot-crowding-curve-convexity
description: "Evaluate CFTC Positioning Concentration and Commodity Curve Convexity with a time-vintaged baseline, feasibility constraints and economic falsification."
---
# SKILL — CFTC Positioning Concentration and Commodity Curve Convexity
## Trigger
Use this skill when researching: **Scale futures trend/curve exposure after weekly public positioning releases with pre-set liquidation budgets.** in **United States commodity futures with global supply chains**.

## Inputs
Source/version references and license, decision clock, CFTC contract market × Tuesday reference position × Friday public release, then weekly trade clock, the cost model, allowed actions, and study windows. Minimum fields: CFTC Disaggregated COT futures positions, futures contracts prices/rolls, EIA physical inventories where applicable..

## Procedure
1. Load SPEC and HANDOFF; state hypothesis and category B · Domestic & global markets.
2. Build source-claim ledger. Do not conflate official data description and available executable market dataset.
3. Check first public availability and carry correction vintages forward, never backward.
4. Create adverse synthetic fixtures and reject invalid market constraints.
5. Fit and run **Futures curve carry/roll-yield and 12-month time-series momentum.** on training data with full costs.
6. Define **Positioning-conditioned conditional expected shortfall regression.**, plus optional **Stochastic inventory-demand equilibrium with nonlinear dealer hedging and curve impact.** conditional on simple model advantage.
7. Freeze chronological holdouts and evaluate **tail loss reduction, annualized Sharpe after roll/slippage, opportunity-cost drag and hedge stability.** plus capacity and tail risk.
8. Try to falsify: **Reject if tail-risk control does not beat carry/momentum or negative convexity effect changes sign in out-of-sample contracts.**.
9. Record all negative tests, unverified sources, measured trade-offs and manual approval gate.
10. Return BLOCKED if CFTC taxonomy changes, combined report double-counting and slow publication may annihilate predictive edge. cannot be mitigated.

## Artifacts and failure behavior
Future proposed artifacts: `run_manifest.json`, `source_claim_ledger.md`, `costed_baseline.json`, `paired_evaluation.json`, `human_review.md`.
None are presently created by this design. Never report historical profits, tests passed or production promotion without evidence.
