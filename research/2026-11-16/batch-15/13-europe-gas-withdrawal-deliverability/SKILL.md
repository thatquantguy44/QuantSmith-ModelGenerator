---
name: research-europe-gas-withdrawal-deliverability
description: Design or evaluate european gas storage deliverability hedge for Germany, Netherlands, Italy and European gas hubs; use for the stated economic decision, point-in-time data audit, baseline challenge and falsification gates. Research workflow only; not a deployed runtime.
---

# Research European Gas Storage Deliverability Hedge

1. State the decision: Hedge winter peak gas-delivery risk using facility-level withdrawal constraints rather than national percent-full alone. Read SPEC for `QMG-20261116-13` requirements and EVALS for the frozen gate before selecting a model.
2. Resolve public sources in SOURCES first. Use storage facility x gas day x publication version; reject unlicensed payloads and missing publication times. Preserve observed, published, received, available and effective times separately.
3. Align inputs to this clock: Recompute after first verified daily publication; execute next liquid hub session with at least one-day lag when historical publication time is unknown. Revised storage values never replace first-release features. Build withdrawal headroom, gas-day inventory state and hub connectivity. Keep future outcomes and later amendments out of features.
4. Reproduce the baseline: Hedge ratio proportional to national percent-full deficit relative to trailing seasonal average. Match risk, costs, sample, execution clock and permitted actions before testing Constrained physical storage network and linear hedge projection.
5. Run the domain negative test: Create two facilities with identical percent-full and different withdrawal limits: shortage outputs must differ. Remove one interconnector and forbid unphysical gas flows. Stop on any future-data acceptance or hard-constraint violation.
6. Challenge the hypothesis: A deliverability-weighted storage index reduces winter peak procurement CVaR by at least 10% versus a percent-full rule at equal average hedge cost. Apply exactly: GO if >=10% CVaR reduction at equal mean cost across >=5 winters including one held-out stressed winter; STOP if results reverse under plausible deliverability curves or cross-border restrictions. Report all failed variants and effective independent sample size.
7. Review Illustrative $30m annual hedge exposure; use <=1% lagged hub/spread volume and explicit spread liquidity. USD ROI translates net EUR procurement savings at hedged rates; no assumed storage ownership. Recompute the purely illustrative ROI using measured cost evidence if available; otherwise retain the assumption label and negative scenarios.
8. Return deliverability risk index and constrained seasonal hedge weights, uncertainty, source lineage and a GO/STOP/BLOCKED verdict. Escalate Reported maximum withdrawal is not necessarily sustainable at low fill. Regional bottlenecks and revisions dominate; proxy futures do not deliver facility access. Never trade, change contracts, deploy or claim empirical completion from this document alone.

Use PLAN for adapter boundaries and TASKS for traceability; retain immutable manifests and dependency locks when implementation is later authorized. This repository workflow is not installed as a personal ChatGPT skill.
