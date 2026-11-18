---
name: research-south-africa-power-outage-cashflows
description: Design or evaluate south african power reliability equity exposure for South Africa; JSE industrials, retailers and exporters; use for the stated economic decision, point-in-time data audit, baseline challenge and falsification gates. Research workflow only; not a deployed runtime.
---

# Research South African Power Reliability Equity Exposure

1. State the decision: Build a sector/beta-neutral equity hedge against power-supply deterioration using pre-disclosed operational exposure. Read SPEC for `QMG-20261116-17` requirements and EVALS for the frozen gate before selecting a model.
2. Resolve public sources in SOURCES first. Use firm x day and dated generation/outage release; reject unlicensed payloads and missing publication times. Preserve observed, published, received, available and effective times separately.
3. Align inputs to this clock: Update after verified Eskom publication; act next JSE session with prior-disclosed firm exposures. Never label realized electricity usage as known before earnings disclosure. Build pre-disclosed energy intensity, backup coverage and released outage innovation. Keep future outcomes and later amendments out of features.
4. Reproduce the baseline: National load-shedding stage interacted with fixed sector averages and a market/FX hedge. Match risk, costs, sample, execution clock and permitted actions before testing Panel fixed effects with pre-period exposure interactions and event-placebo tests.
5. Run the domain negative test: Use a future outage series as a placebo and randomize exposure labels within sectors; the real-time pipeline must reject future features and significance should vanish under label randomization. Stop on any future-data acceptance or hard-constraint violation.
6. Challenge the hypothesis: Exposure-weighted unplanned generation losses explain cash-flow/return sensitivity beyond national load-shedding stage, improving an outage hedge's downside loss by at least 10%. Apply exactly: GO if downside hedge error improves >=10%, coefficient sign is stable in held-out periods and net benefit survives doubled spreads; STOP causal interpretation if pretrends or commodity/FX confounds remain. Report all failed variants and effective independent sample size.
7. Review Illustrative $20m hedge sleeve capped at 1% ADV with local spreads, market access and ZAR hedge costs; concentrated names can exhaust capacity rapidly. Recompute the purely illustrative ROI using measured cost evidence if available; otherwise retain the assumption label and negative scenarios.
8. Return firm sensitivity bounds and neutral power-risk hedge research basket, uncertainty, source lineage and a GO/STOP/BLOCKED verdict. Escalate Power failures can reflect economic demand and maintenance choices; common national shocks do not supply clean quasi-random variation. Firms adopting solar are selected, and disclosure histories are incomplete. Never trade, change contracts, deploy or claim empirical completion from this document alone.

Use PLAN for adapter boundaries and TASKS for traceability; retain immutable manifests and dependency locks when implementation is later authorized. This repository workflow is not installed as a personal ChatGPT skill.
