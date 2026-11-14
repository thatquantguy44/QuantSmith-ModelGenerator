---
name: weather-electricity-gas-forecast-revisions
description: "Evaluate Weather Forecast Revision as an Electricity-to-Gas Risk Hedge with a time-vintaged baseline, feasibility constraints and economic falsification."
---
# SKILL — Weather Forecast Revision as an Electricity-to-Gas Risk Hedge
## Trigger
Use this skill when researching: **Size gas/power-linked hedges using only prior-issued weather forecasts and expected net-load revisions.** in **US regional power markets and Henry Hub-linked energy**.

## Inputs
Source/version references and license, decision clock, balancing authority × weather forecast issuance × lead hour, the cost model, allowed actions, and study windows. Minimum fields: NWS issued and archived forecasts, EIA balancing authority hourly load and generation, power/gas futures settlements and basis..

## Procedure
1. Load SPEC and HANDOFF; state hypothesis and category B · Domestic & global markets.
2. Build source-claim ledger. Do not conflate official data description and available executable market dataset.
3. Check first public availability and carry correction vintages forward, never backward.
4. Create adverse synthetic fixtures and reject invalid market constraints.
5. Fit and run **Seasonal degree-day demand regression and absolute temperature forecasts.** on training data with full costs.
6. Define **Net-load forecast-revision elasticity with non-linear stress threshold.**, plus optional **Probabilistic shortfall-and-constraint model with weather ensemble calibration.** conditional on simple model advantage.
7. Freeze chronological holdouts and evaluate **load p95 quantile loss, probabilistic calibration, hedge tracking error, net futures carry.** plus capacity and tail risk.
8. Try to falsify: **Reject if no improvements in forecast quantile loss or hedge after-cost variance over degrees-day baseline.**.
9. Record all negative tests, unverified sources, measured trade-offs and manual approval gate.
10. Return BLOCKED if Archive of *historical forecasts as issued* may be inaccessible; today's historical observations are not contemporaneous forecasts. cannot be mitigated.

## Artifacts and failure behavior
Future proposed artifacts: `run_manifest.json`, `source_claim_ledger.md`, `costed_baseline.json`, `paired_evaluation.json`, `human_review.md`.
None are presently created by this design. Never report historical profits, tests passed or production promotion without evidence.
