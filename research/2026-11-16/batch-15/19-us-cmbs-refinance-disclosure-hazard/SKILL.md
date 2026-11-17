---
name: research-us-cmbs-refinance-disclosure-hazard
description: Design or evaluate us cmbs refinance hazard from public disclosures for United States commercial property and securitized credit; use for the stated economic decision, point-in-time data audit, baseline challenge and falsification gates. Research workflow only; not a deployed runtime.
---

# Research US CMBS Refinance Hazard from Public Disclosures

1. State the decision: Limit public CMBS/REIT credit exposure according to released refinance cash-flow gaps and competing maturity outcomes. Read SPEC for `QMG-20261116-19` requirements and EVALS for the frozen gate before selecting a model.
2. Resolve public sources in SOURCES first. Use loan x public reporting vintage x maturity/outcome event; reject unlicensed payloads and missing publication times. Preserve observed, published, received, available and effective times separately.
3. Align inputs to this clock: Update risk after SEC acceptance plus one business day parsing/review; a prior reporting month's NOI remains unavailable until filing. Amendments are appended and never rewrite earlier risk snapshots. Build public refinance cash gap, maturity hazard and amendment lineage. Keep future outcomes and later amendments out of features.
4. Reproduce the baseline: Logistic distress model using months-to-maturity and last publicly available DSCR with fixed rate-shock scenarios. Match risk, costs, sample, execution clock and permitted actions before testing Competing-risk survival model with refinance cash-gap covariates.
5. Run the domain negative test: Replace an original loan maturity with a later extension and verify earlier features remain unchanged; include liquidated loans and enforce waterfall conservation under default scenarios. Stop on any future-data acceptance or hard-constraint violation.
6. Challenge the hypothesis: A vintage-safe competing-risk model improves 12-month refinancing-distress Brier score by at least 10% versus maturity wall plus current DSCR and lowers stress portfolio loss by 5% at equal spread carry. Apply exactly: GO if Brier improves >=10% and stress loss falls >=5% at same carry over a held-out issuance vintage; STOP if modification histories, exited loans or outcome timing are missing for >10% of sample. Report all failed variants and effective independent sample size.
7. Review Illustrative $50m credit exposure; position limits depend on tranche liquidity and loss subordination. No assumption that a loan risk score is directly tradable or every CMBS has a liquid hedge. Recompute the purely illustrative ROI using measured cost evidence if available; otherwise retain the assumption label and negative scenarios.
8. Return competing-outcome probabilities, missing-field coverage and tranche mapping limits, uncertainty, source lineage and a GO/STOP/BLOCKED verdict. Escalate Surviving securitizations and amended files omit failed/removed loans; appraisals lag. Tranche waterfalls and selection into public deals prevent loan-level risk from mapping directly to bond P&L. Never trade, change contracts, deploy or claim empirical completion from this document alone.

Use PLAN for adapter boundaries and TASKS for traceability; retain immutable manifests and dependency locks when implementation is later authorized. This repository workflow is not installed as a personal ChatGPT skill.
