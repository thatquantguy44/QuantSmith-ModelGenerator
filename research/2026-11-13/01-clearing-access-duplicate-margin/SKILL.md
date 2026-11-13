---
name: clearing-access-duplicate-margin
description: "Evaluate Treasury Clearing Access-Path & Duplicate-Margin Optimizer with a time-vintaged baseline, feasibility constraints and economic falsification."
---
# SKILL — Treasury Clearing Access-Path & Duplicate-Margin Optimizer
## Trigger
Use this skill when researching: **Route eligible Treasury financing activity among legally permitted clearing access paths and participant entities while honoring CCP and customer-protection constraints.** in **United States; cleared cash Treasury and repo**.

## Inputs
Source/version references and license, decision clock, trade × eligible clearing access path × decision timestamp, the cost model, allowed actions, and study windows. Minimum fields: Eligible trade templates; path availability; historical quote spreads; initial/variation margin stress; capital/CCLF allocation; modeled netting sets; direct/sponsored/agent fees..

## Procedure
1. Load SPEC and HANDOFF; state hypothesis and category A · Securities finance.
2. Build source-claim ledger. Do not conflate official data description and available executable market dataset.
3. Check first public availability and carry correction vintages forward, never backward.
4. Create adverse synthetic fixtures and reject invalid market constraints.
5. Fit and run **Minimize executable repo rate ignoring path-specific costs, after validating that every route is eligible.** on training data with full costs.
6. Define **Mixed-integer convex routing with separate margin, settlement and liquidity shadow prices.**, plus optional **Stochastic two-stage CCP-margin and default-fund planning with cross-netting robustness.** conditional on simple model advantage.
7. Freeze chronological holdouts and evaluate **USD all-in funding cost, dollar liquidity encumbrance, margin stress p99, ineligible route count, rejection rate.** plus capacity and tail risk.
8. Try to falsify: **Reject if simulated net savings are below 2 bps of affected financing notional or vanish under independently validated margin rules.**.
9. Record all negative tests, unverified sources, measured trade-offs and manual approval gate.
10. Return BLOCKED if Clearing rule exemptions and netting eligibility vary; estimated margin offsets could be nonportable across entities. cannot be mitigated.

## Artifacts and failure behavior
Future proposed artifacts: `run_manifest.json`, `source_claim_ledger.md`, `costed_baseline.json`, `paired_evaluation.json`, `human_review.md`.
None are presently created by this design. Never report historical profits, tests passed or production promotion without evidence.
