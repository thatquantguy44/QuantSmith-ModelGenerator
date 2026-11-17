---
name: research-sterling-iltr-maturity-ladder
description: Design or evaluate sterling iltr auction demand smoothing for United Kingdom; GBP central-bank secured liquidity; use for the stated economic decision, point-in-time data audit, baseline challenge and falsification gates. Research workflow only; not a deployed runtime.
---

# Research Sterling ILTR Auction Demand Smoothing

1. State the decision: Distribute a fixed eligible reserve requirement across future ILTR auctions and collateral sets without assuming a strategic low bid improves the clearing price. Read SPEC for `QMG-20261116-03` requirements and EVALS for the frozen gate before selecting a model.
2. Resolve public sources in SOURCES first. Use auction x collateral set x release version; reject unlicensed payloads and missing publication times. Preserve observed, published, received, available and effective times separately.
3. Align inputs to this clock: Use results only after public release; plan by 09:00 Europe/London before an operation using earlier operations and latest approved reserve forecast. Verify each current auction deadline before a live pilot. Build clearing-spread intervals, reserve coverage and maturity bucket exposure. Keep future outcomes and later amendments out of features.
4. Reproduce the baseline: Equal weekly maturities with bids at independently approved maximum willingness-to-pay; compare a single-auction funding plan separately. Match risk, costs, sample, execution clock and permitted actions before testing Shape-constrained aggregate supply-curve estimation plus stochastic ladder optimization.
5. Run the domain negative test: Replace the estimated supply curve with a flat curve: the model must not claim auction-price savings from moving a price-taking bid. Stop on any future-data acceptance or hard-constraint violation.
6. Challenge the hypothesis: Demand smoothing lowers all-in expected funding expense by at least 1 bp relative to a single-auction ladder while preserving liquidity coverage under adverse allocation outcomes. Apply exactly: GO if >=1 bp net annualized saving versus equal ladder in >=12 held-out operations and no stressed reserve shortfall. STOP if all plausible demand curves imply the same ladder or savings require underbidding actual willingness-to-pay. Report all failed variants and effective independent sample size.
7. Review Illustrative GBP500m reserve need in USD-equivalent ROI; size must be small relative to auction capacity or explicitly model own impact. Operational access, collateral prepositioning and bridge-funding limits bind. Recompute the purely illustrative ROI using measured cost evidence if available; otherwise retain the assumption label and negative scenarios.
8. Return auction cash-demand ladder with allocation sensitivity bounds, uncertainty, source lineage and a GO/STOP/BLOCKED verdict. Escalate Aggregate clearing outcomes do not identify individual demand or fill probabilities. Facility calibration changes can invalidate extrapolation; official participation rules take precedence. Never trade, change contracts, deploy or claim empirical completion from this document alone.

Use PLAN for adapter boundaries and TASKS for traceability; retain immutable manifests and dependency locks when implementation is later authorized. This repository workflow is not installed as a personal ChatGPT skill.
