---
name: repo-market-fragmentation-nowcast
description: "Evaluate Cleared Versus Tri-Party Repo Fragmentation Nowcast with a time-vintaged baseline, feasibility constraints and economic falsification."
---
# SKILL — Cleared Versus Tri-Party Repo Fragmentation Nowcast
## Trigger
Use this skill when researching: **Adjust next-day funding risk overlays and desk liquidity buffers based on *publication-time* inter-venue segmentation rather than guessed live spreads.** in **United States short-term funding markets**.

## Inputs
Source/version references and license, decision clock, venue × collateral class × tenor × underlying observation date, plus public publication timestamp, the cost model, allowed actions, and study windows. Minimum fields: OFR cleared and tri-party rate-volume series; collateral categories; SOFR; weekly dealer aggregate financing; release metadata..

## Procedure
1. Load SPEC and HANDOFF; state hypothesis and category A · Securities finance.
2. Build source-claim ledger. Do not conflate official data description and available executable market dataset.
3. Check first public availability and carry correction vintages forward, never backward.
4. Create adverse synthetic fixtures and reject invalid market constraints.
5. Fit and run **SOFR level change and aggregate funding volume z-score.** on training data with full costs.
6. Define **State-space latent fragmentation index with lag-aware missingness.**, plus optional **Hierarchical online change-point and causal regime attribution by venue and reporting channel.** conditional on simple model advantage.
7. Freeze chronological holdouts and evaluate **next-session stress AUPRC, calibrated Brier score, false alarm rate, funding stress drawdown.** plus capacity and tail risk.
8. Try to falsify: **Reject if lag-safe AUPRC does not exceed SOFR-only benchmark by 0.03 on an untouched crisis/quiet holdout.**.
9. Record all negative tests, unverified sources, measured trade-offs and manual approval gate.
10. Return BLOCKED if Revised/missing suppressed OFR cells and cross-venue holiday timing can create lookahead and artificial divergences. cannot be mitigated.

## Artifacts and failure behavior
Future proposed artifacts: `run_manifest.json`, `source_claim_ledger.md`, `costed_baseline.json`, `paired_evaluation.json`, `human_review.md`.
None are presently created by this design. Never report historical profits, tests passed or production promotion without evidence.
