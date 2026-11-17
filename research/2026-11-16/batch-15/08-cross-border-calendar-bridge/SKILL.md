---
name: research-cross-border-calendar-bridge
description: Design or evaluate cross-border settlement calendar bridge planner for US, euro area and UK financing settlement; use for the stated economic decision, point-in-time data audit, baseline challenge and falsification gates. Research workflow only; not a deployed runtime.
---

# Research Cross-Border Settlement Calendar Bridge Planner

1. State the decision: Choose an earlier settlement date and minimal bridge cash for already approved cross-border obligations. Read SPEC for `QMG-20261116-08` requirements and EVALS for the frozen gate before selecting a model.
2. Resolve public sources in SOURCES first. Use obligation leg x settlement service x UTC instant; reject unlicensed payloads and missing publication times. Preserve observed, published, received, available and effective times separately.
3. Align inputs to this clock: Plan at least two local business days before a known holiday, using rules announced by then. Unexpected outages are separate stress scenarios; announced future changes enter only after their publication. Build service open intervals, version effective dates, cash-day gaps and DST conversion. Keep future outcomes and later amendments out of features.
4. Reproduce the baseline: Prefund every cross-border obligation two generic business days early, with manual holiday review. Match risk, costs, sample, execution clock and permitted actions before testing Time-expanded multi-service cash-flow network.
5. Run the domain negative test: Replay US/Europe DST mismatch, Good Friday and a service-specific cutoff extension; the planner must distinguish securities and cash service availability. Stop on any future-data acceptance or hard-constraint violation.
6. Challenge the hypothesis: A service-specific dated-calendar planner eliminates at least 90% of calendar-caused exceptions and lowers bridge funding cost by 10% versus a fixed two-business-day prefunding rule. Apply exactly: GO if >=90% calendar exceptions avoided and >=10% net bridge-cost saving on >=24 holiday windows; zero infeasible settlement recommendations. STOP if routing assumptions require unapproved service access. Report all failed variants and effective independent sample size.
7. Review Illustrative $200m annual recurring bridge balances in USD equivalent; same approved obligations, no new FX carry position. Saving bounded by actual overlap days and bridge rates. Recompute the purely illustrative ROI using measured cost evidence if available; otherwise retain the assumption label and negative scenarios.
8. Return prefunding dates, minimal cash bridge and infeasible-leg alerts, uncertainty, source lineage and a GO/STOP/BLOCKED verdict. Escalate Future operating-day changes differ between funds and securities services. DST, half-days and local date conventions can introduce 24-hour errors; a public calendar is not a service entitlement. Never trade, change contracts, deploy or claim empirical completion from this document alone.

Use PLAN for adapter boundaries and TASKS for traceability; retain immutable manifests and dependency locks when implementation is later authorized. This repository workflow is not installed as a personal ChatGPT skill.
