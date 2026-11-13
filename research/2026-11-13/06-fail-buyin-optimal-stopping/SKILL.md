---
name: fail-buyin-optimal-stopping
description: "Evaluate Settlement-Fail Buy-In versus Wait Optimal Stopping with a time-vintaged baseline, feasibility constraints and economic falsification."
---
# SKILL — Settlement-Fail Buy-In versus Wait Optimal Stopping
## Trigger
Use this skill when researching: **For an already-failed settlement instruction, decide when to cover, reroute or await delivery under documented close-out rules.** in **US Treasury and agency settlement**.

## Inputs
Source/version references and license, decision clock, failed settlement instruction × elapsed failed day × cut-off timestamp, the cost model, allowed actions, and study windows. Minimum fields: Public dealer failure aggregates for calibration; synthetic failure life histories; approved buy-in quotes, fails charges and legal remedies..

## Procedure
1. Load SPEC and HANDOFF; state hypothesis and category A · Securities finance.
2. Build source-claim ledger. Do not conflate official data description and available executable market dataset.
3. Check first public availability and carry correction vintages forward, never backward.
4. Create adverse synthetic fixtures and reject invalid market constraints.
5. Fit and run **Auto-escalate after fixed N-day failure age.** on training data with full costs.
6. Define **Discrete-time survival model with exact dynamic-programming stopping rule.**, plus optional **Partial-observation optimal stopping with supply scarcity and stochastic cover price.** conditional on simple model advantage.
7. Freeze chronological holdouts and evaluate **resolved failure days, total cure cost, forced buy-in count, missed deadline, tail loss.** plus capacity and tail risk.
8. Try to falsify: **Reject if holdout cost savings are below 5% or any mandated deadline is missed.**.
9. Record all negative tests, unverified sources, measured trade-offs and manual approval gate.
10. Return BLOCKED if Fails charges and rights to enforce buy-ins differ by asset, market and contract; wrong assumptions invalidate decisions. cannot be mitigated.

## Artifacts and failure behavior
Future proposed artifacts: `run_manifest.json`, `source_claim_ledger.md`, `costed_baseline.json`, `paired_evaluation.json`, `human_review.md`.
None are presently created by this design. Never report historical profits, tests passed or production promotion without evidence.
