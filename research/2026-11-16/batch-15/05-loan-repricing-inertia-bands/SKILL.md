---
name: research-loan-repricing-inertia-bands
description: Design or evaluate stock-loan repricing bands with relationship friction for United States and developed-Europe equity loans; use for the stated economic decision, point-in-time data audit, baseline challenge and falsification gates. Research workflow only; not a deployed runtime.
---

# Research Stock-Loan Repricing Bands with Relationship Friction

1. State the decision: Choose a fee-change threshold and batching cadence for existing loans rather than repricing every observed basis-point move. Read SPEC for `QMG-20261116-05` requirements and EVALS for the frozen gate before selecting a model.
2. Resolve public sources in SOURCES first. Use loan x repricing proposal/response event; reject unlicensed payloads and missing publication times. Preserve observed, published, received, available and effective times separately.
3. Align inputs to this clock: Review at 10:00 local market time with benchmark releases and acknowledgments available by 09:55. Use an effective fee only after both contractual acceptance and booking; no retroactive filled proposals. Build fee gap, duration in band, response propensity and net processing cost. Keep future outcomes and later amendments out of features.
4. Reproduce the baseline: Match yesterday's observable benchmark daily, with contractual limits; also compare a fixed 10-bp band. Match risk, costs, sample, execution clock and permitted actions before testing Impulse-control dynamic program with survival-calibrated borrower exits.
5. Run the domain negative test: Set negotiation and exit costs to zero: the optimal inaction band should collapse under an otherwise frictionless model; rejected proposals must never become realized fees. Stop on any future-data acceptance or hard-constraint violation.
6. Challenge the hypothesis: A two-sided repricing band increases net relationship-adjusted revenue by at least 5% versus daily benchmark matching without reducing risk-adjusted balances by more than 2%. Apply exactly: GO if >=5% net revenue improvement with bootstrap lower bound >0 and balance loss <=2% in a pre-registered eligible cohort; no subgroup >5% deterioration. STOP if benefit relies on unobserved rejected requests or violates agreed repricing rights. Report all failed variants and effective independent sample size.
7. Review Illustrative $400m existing balances; not a new trading strategy. Control concentration and fee elasticity; bps benefit must be net of exits, source revenue sharing and labor. Recompute the purely illustrative ROI using measured cost evidence if available; otherwise retain the assumption label and negative scenarios.
8. Return hold/reprice recommendation, approved band and counterfactual uncertainty, uncertainty, source lineage and a GO/STOP/BLOCKED verdict. Escalate Repricing is endogenous to scarcity and relationship quality. Off-policy evaluation cannot fix zero action overlap; randomized eligible shadow suggestions need business approval. Never trade, change contracts, deploy or claim empirical completion from this document alone.

Use PLAN for adapter boundaries and TASKS for traceability; retain immutable manifests and dependency locks when implementation is later authorized. This repository workflow is not installed as a personal ChatGPT skill.
