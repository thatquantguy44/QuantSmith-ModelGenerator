---
name: trade-network-export-shocks
description: "Evaluate Trade-Network Export-Shock Transmission to Equity Sectors with a time-vintaged baseline, feasibility constraints and economic falsification."
---
# SKILL — Trade-Network Export-Shock Transmission to Equity Sectors
## Trigger
Use this skill when researching: **Adjust public-market sector risk or hedges using time-valid trade-network concentration shocks, not a blunt GDP exposure factor.** in **US, Mexico, Germany, Japan, Korea, China and ASEAN markets**.

## Inputs
Source/version references and license, decision clock, reporter × partner × HS code × reference month × publication/availability timestamp, the cost model, allowed actions, and study windows. Minimum fields: UN Comtrade reported and partner-reported trade by HS code/month; sector country revenue mix; FX; sector returns and macro controls..

## Procedure
1. Load SPEC and HANDOFF; state hypothesis and category B · Domestic & global markets.
2. Build source-claim ledger. Do not conflate official data description and available executable market dataset.
3. Check first public availability and carry correction vintages forward, never backward.
4. Create adverse synthetic fixtures and reject invalid market constraints.
5. Fit and run **Equal-weight country sector allocation with FX and local industrial production controls.** on training data with full costs.
6. Define **Sparse directed trade graph factor with event-lag-aware regressions.**, plus optional **Causal graph neural propagation with hard release-vintage masking and sector earnings transmission.** conditional on simple model advantage.
7. Freeze chronological holdouts and evaluate **OOS sector information coefficient, dollar-neutral Sharpe, earnings revision hit rate, turnover and tail loss.** plus capacity and tail risk.
8. Try to falsify: **Reject if positive net cross-country IC is not stable in each of two disjoint geographic holdouts or after publication lags.**.
9. Record all negative tests, unverified sources, measured trade-offs and manual approval gate.
10. Return BLOCKED if Revisions, late reporters, trade re-exports and mapping HS codes to listed firms can create survivorship and spurious exposure. cannot be mitigated.

## Artifacts and failure behavior
Future proposed artifacts: `run_manifest.json`, `source_claim_ledger.md`, `costed_baseline.json`, `paired_evaluation.json`, `human_review.md`.
None are presently created by this design. Never report historical profits, tests passed or production promotion without evidence.
