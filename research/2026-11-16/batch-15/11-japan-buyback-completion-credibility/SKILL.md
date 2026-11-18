---
name: research-japan-buyback-completion-credibility
description: Design or evaluate japan buyback completion credibility for Japan listed equities; developed-market event research; use for the stated economic decision, point-in-time data audit, baseline challenge and falsification gates. Research workflow only; not a deployed runtime.
---

# Research Japan Buyback Completion Credibility

1. State the decision: Weight an announcement-event equity sleeve by ex-ante completion probability rather than headline authorized buyback size. Read SPEC for `QMG-20261116-11` requirements and EVALS for the frozen gate before selecting a model.
2. Resolve public sources in SOURCES first. Use issuer x announced buyback program x filing acceptance event; reject unlicensed payloads and missing publication times. Preserve observed, published, received, available and effective times separately.
3. Align inputs to this clock: Enter at next Tokyo session VWAP after a public announcement plus 30 minutes processing; filings arriving after the next-open cutoff shift another session. Completion reports update only when publicly filed. Build prior completion rate, cash-funded capacity, expiry horizon and free-float-normalized authorization. Keep future outcomes and later amendments out of features.
4. Reproduce the baseline: Authorization divided by contemporaneously known float market cap, with the same neutral portfolio and execution rules. Match risk, costs, sample, execution clock and permitted actions before testing Calibrated discrete-time completion hazard with constrained event portfolio.
5. Run the domain negative test: Shift completion filings to their reporting-period end: leakage checker must reject the join; include terminated programs and delisted issuers with zero future authorization assumed. Stop on any future-data acceptance or hard-constraint violation.
6. Challenge the hypothesis: Completion-weighted signals improve 60-trading-day sector/beta-neutral net returns by at least 50 bps per annum versus authorization-size signals, after 30 bps round-trip costs. Apply exactly: GO if completion Brier improves >=10% and net return uplift >=50 annualized bps with block-bootstrap lower bound >0 over >=200 programs and a held-out year; STOP on missing delistings or gains concentrated in inaccessible prints. Report all failed variants and effective independent sample size.
7. Review Illustrative $25m beta-neutral sleeve; cap each trade at 1% of lagged ADV, use local spreads, impact and shorting costs. Thin small-cap programs may have little scalable edge. Recompute the purely illustrative ROI using measured cost evidence if available; otherwise retain the assumption label and negative scenarios.
8. Return completion probabilities and neutral event-sleeve research orders, uncertainty, source lineage and a GO/STOP/BLOCKED verdict. Escalate Completion is endogenous to stock prices, governance changes and earnings; predictive results do not establish buyback causation. Current issuer lists produce survivorship bias. Never trade, change contracts, deploy or claim empirical completion from this document alone.

Use PLAN for adapter boundaries and TASKS for traceability; retain immutable manifests and dependency locks when implementation is later authorized. This repository workflow is not installed as a personal ChatGPT skill.
