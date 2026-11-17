---
name: research-india-index-flow-duration-neutral
description: Design or evaluate india bond index-flow saturation for India government bonds; emerging-market capital flows; use for the stated economic decision, point-in-time data audit, baseline challenge and falsification gates. Research workflow only; not a deployed runtime.
---

# Research India Bond Index-Flow Saturation

1. State the decision: Tilt duration-neutral eligible-versus-near-eligible government bond baskets using dated projected passive demand and realized foreign-flow saturation. Read SPEC for `QMG-20261116-14` requirements and EVALS for the frozen gate before selecting a model.
2. Resolve public sources in SOURCES first. Use government bond x announcement/rebalance cohort x public flow release; reject unlicensed payloads and missing publication times. Preserve observed, published, received, available and effective times separately.
3. Align inputs to this clock: Act next Mumbai session after a verified inclusion announcement or ownership release; close at a predeclared post-effective window. Never use final index weights or future ownership before announcement. Build announced flow pressure, free-float turnover and lagged foreign ownership saturation. Keep future outcomes and later amendments out of features.
4. Reproduce the baseline: Equal-risk inclusion-event basket versus duration-matched eligible controls. Match risk, costs, sample, execution clock and permitted actions before testing Matched staggered event study with demand-pressure interactions.
5. Run the domain negative test: Assign the same event to noneligible placebo bonds and to dates six months earlier; no persistent significant effect should survive cohort-level multiple-testing adjustment. Stop on any future-data acceptance or hard-constraint violation.
6. Challenge the hypothesis: Expected demand scaled by free-float turnover predicts inclusion-window residual returns better than an inclusion dummy, and improves net basket return by at least 20 bps per annum. Apply exactly: GO if >=20 net annualized bps improvement and event-cluster confidence lower bound >0; pretrends must pass a specified +/-10 bp equivalence band. STOP if fewer than 3 independent cohorts or ownership/AUM histories are reconstructed retrospectively. Report all failed variants and effective independent sample size.
7. Review Illustrative $50m duration-neutral basket, capped at 1% issue turnover with market access and FX hedging charged. Passive flow estimates are not executable demand guarantees. Recompute the purely illustrative ROI using measured cost evidence if available; otherwise retain the assumption label and negative scenarios.
8. Return event-study estimands, placebo diagnostics and duration-neutral research basket, uncertainty, source lineage and a GO/STOP/BLOCKED verdict. Escalate Eligibility correlates with liquidity and issuance; parallel trends may fail. Single historical inclusion episodes cannot support strong causal or scalable trading claims. Never trade, change contracts, deploy or claim empirical completion from this document alone.

Use PLAN for adapter boundaries and TASKS for traceability; retain immutable manifests and dependency locks when implementation is later authorized. This repository workflow is not installed as a personal ChatGPT skill.
