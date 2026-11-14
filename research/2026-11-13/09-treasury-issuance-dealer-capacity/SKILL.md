---
name: treasury-issuance-dealer-capacity
description: "Evaluate Treasury Issuance-to-Dealer Intermediation Capacity Map with a time-vintaged baseline, feasibility constraints and economic falsification."
---
# SKILL — Treasury Issuance-to-Dealer Intermediation Capacity Map
## Trigger
Use this skill when researching: **Set research-level short-term Treasury liquidity stress overlays around security supply events, independent of day-of-quarter calendar effects.** in **United States issuance and dealer system**.

## Inputs
Source/version references and license, decision clock, issuance cohort × week of publicly released dealer aggregates, the cost model, allowed actions, and study windows. Minimum fields: Treasury auction issuance and settlement schedule; weekly primary dealer net positions/financing; OFR repo aggregates; public Treasury yield changes..

## Procedure
1. Load SPEC and HANDOFF; state hypothesis and category A · Securities finance.
2. Build source-claim ledger. Do not conflate official data description and available executable market dataset.
3. Check first public availability and carry correction vintages forward, never backward.
4. Create adverse synthetic fixtures and reject invalid market constraints.
5. Fit and run **Treasury yield volatility and calendar week indicators.** on training data with full costs.
6. Define **Event-study + state-space dealer supply absorption proxy.**, plus optional **Instrumented quasi-experiment using prescheduled auction supply shocks and cross-CUSIP constraints.** conditional on simple model advantage.
7. Freeze chronological holdouts and evaluate **stress forecast Brier, AUPRC, lead-time, false positives and hedge drawdown.** plus capacity and tail risk.
8. Try to falsify: **Reject if no improvement over the rate-volatility-only benchmark on genuinely held-out issuance regimes.**.
9. Record all negative tests, unverified sources, measured trade-offs and manual approval gate.
10. Return BLOCKED if Aggregate dealer reports cannot identify securities or dealers and issuance is endogenous to financing conditions. cannot be mitigated.

## Artifacts and failure behavior
Future proposed artifacts: `run_manifest.json`, `source_claim_ledger.md`, `costed_baseline.json`, `paired_evaluation.json`, `human_review.md`.
None are presently created by this design. Never report historical profits, tests passed or production promotion without evidence.
