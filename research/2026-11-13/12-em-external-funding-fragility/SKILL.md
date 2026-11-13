---
name: em-external-funding-fragility
description: "Evaluate EM External-Funding Fragility via Currency Mismatch and IIP with a time-vintaged baseline, feasibility constraints and economic falsification."
---
# SKILL — EM External-Funding Fragility via Currency Mismatch and IIP
## Trigger
Use this skill when researching: **Size EM FX downside budgets and sovereign duration exposures before external-funding shocks.** in **Brazil, Mexico, South Africa, Indonesia, India and selected EM sovereigns**.

## Inputs
Source/version references and license, decision clock, country × reporting quarter × first-public-availability time, the cost model, allowed actions, and study windows. Minimum fields: IMF IIP, BIS global liquidity quarterly FX credit, OECD macro where available, public reserve series and FX/sovereign returns..

## Procedure
1. Load SPEC and HANDOFF; state hypothesis and category B · Domestic & global markets.
2. Build source-claim ledger. Do not conflate official data description and available executable market dataset.
3. Check first public availability and carry correction vintages forward, never backward.
4. Create adverse synthetic fixtures and reject invalid market constraints.
5. Fit and run **Traditional sovereign credit rating tier, FX carry and three-month realized volatility.** on training data with full costs.
6. Define **Point-in-time standardized funding mismatch factor with recession/regime interactions.**, plus optional **Joint skewed macro-financial state-space with robust optimization and missing vintage uncertainty.** conditional on simple model advantage.
7. Freeze chronological holdouts and evaluate **EM FX crash recall, max drawdown, FX-adjusted stress Brier, portfolio VaR breaches.** plus capacity and tail risk.
8. Try to falsify: **Reject if stress recall or drawdown control fails to beat carry-vol baseline in holdout crises.**.
9. Record all negative tests, unverified sources, measured trade-offs and manual approval gate.
10. Return BLOCKED if Global liquidity metrics are quarterly; imputed weekly updates are model estimates, not observations. cannot be mitigated.

## Artifacts and failure behavior
Future proposed artifacts: `run_manifest.json`, `source_claim_ledger.md`, `costed_baseline.json`, `paired_evaluation.json`, `human_review.md`.
None are presently created by this design. Never report historical profits, tests passed or production promotion without evidence.
