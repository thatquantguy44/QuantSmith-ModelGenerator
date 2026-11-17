---
name: research-global-volatility-corridor-jump-budget
description: Design or evaluate us–europe corridor variance and jump-risk budget for US S&P 500 and euro-area equity index options; use for the stated economic decision, point-in-time data audit, baseline challenge and falsification gates. Research workflow only; not a deployed runtime.
---

# Research US–Europe Corridor Variance and Jump-Risk Budget

1. State the decision: Allocate a limited short-corridor-variance risk budget across US and European indices while purchasing a defined tail hedge. Read SPEC for `QMG-20261116-16` requirements and EVALS for the frozen gate before selecting a model.
2. Resolve public sources in SOURCES first. Use market x option expiry/strike x quote instant plus intraday underlying bars; reject unlicensed payloads and missing publication times. Preserve observed, published, received, available and effective times separately.
3. Align inputs to this clock: Allocate at a common UTC snapshot when both markets have liquid executable quotes; use prior completed return bars only. Do not pair a European close with later US data as contemporaneous. Build corridor variance, overnight jump proxies, executable strip costs and tail hedge Greeks. Keep future outcomes and later amendments out of features.
4. Reproduce the baseline: Equal-vega option-strip variance exposure by market with a fixed put-spread tail hedge and identical costs. Match risk, costs, sample, execution clock and permitted actions before testing Semiparametric continuous/jump decomposition and constrained risk-budget allocation.
5. Run the domain negative test: Insert a large overnight gap with no intraday prints: loss and jump exposure must remain visible; an apparent free option caused by zero/stale bid must be rejected. Stop on any future-data acceptance or hard-constraint violation.
6. Challenge the hypothesis: A corridor/jump-aware allocation reduces 99% tail loss by at least 15% at equal net carry versus equal-vega short-variance with the same tail-hedge budget. Apply exactly: GO if >=15% ES reduction with mean net carry within 5% of baseline across >=8 years including held-out stress; STOP if benefit fails under doubled option spreads or cannot be implemented by listed strips. Report all failed variants and effective independent sample size.
7. Review Illustrative $20m capital budget with explicit vega/margin limits, <=1% option-strike volume/open-interest bounds and no unlimited tail-risk assumption. Capacity likely concentrated in a few liquid expiries. Recompute the purely illustrative ROI using measured cost evidence if available; otherwise retain the assumption label and negative scenarios.
8. Return vega allocation, explicit option-strip positions and stress funding requirements, uncertainty, source lineage and a GO/STOP/BLOCKED verdict. Escalate Sparse extreme events, stale deep-OTM quotes, mid-price replication and model-selected sampling can manufacture carry. Margin calls and holiday mismatches can dominate option premium. Never trade, change contracts, deploy or claim empirical completion from this document alone.

Use PLAN for adapter boundaries and TASKS for traceability; retain immutable manifests and dependency locks when implementation is later authorized. This repository workflow is not installed as a personal ChatGPT skill.
