---
name: research-futures-delivery-inventory-reservation
description: Design or evaluate treasury futures delivery inventory reservation for United States; Treasury futures deliverable baskets and securities loans; use for the stated economic decision, point-in-time data audit, baseline challenge and falsification gates. Research workflow only; not a deployed runtime.
---

# Research Treasury Futures Delivery Inventory Reservation

1. State the decision: Reserve eligible inventory for an existing futures short versus lending it, charging the marginal delivery-option opportunity cost. Read SPEC for `QMG-20261116-04` requirements and EVALS for the frozen gate before selecting a model.
2. Resolve public sources in SOURCES first. Use CUSIP x futures contract x observation timestamp; reject unlicensed payloads and missing publication times. Preserve observed, published, received, available and effective times separately.
3. Align inputs to this clock: Reserve at 15:00 America/Chicago using quotes available by 14:55 and current contract basket version; subsequent delivery notices are outcomes, never predictive features. Build invoice value, basket eligibility and marginal delivery option shadow cost. Keep future outcomes and later amendments out of features.
4. Reproduce the baseline: Hold back 10% of eligible basket inventory and allocate remaining loans using current fees. Match risk, costs, sample, execution clock and permitted actions before testing Scenario dynamic programming for marginal delivery-option value.
5. Run the domain negative test: Freeze the basket to a single security: option-selection value must vanish; change conversion factor units and require invoice identity failure rather than silent rescaling. Stop on any future-data acceptance or hard-constraint violation.
6. Challenge the hypothesis: A delivery-option reserve beats a fixed percentage holdback by at least 2 bps of annualized affected inventory value, after replacement, lending and hedge costs. Apply exactly: GO if >=2 annualized bps saving over fixed holdback across >=8 delivery cycles, no missed delivery and positive benefit at twice observed transaction costs. STOP if gains depend on hindsight cheapest-to-deliver identity. Report all failed variants and effective independent sample size.
7. Review Illustrative $250m affected deliverable inventory. Limited by futures obligation size and deliverable-lot depth; do not take a new directional basis trade merely to generate lending revenue. Recompute the purely illustrative ROI using measured cost evidence if available; otherwise retain the assumption label and negative scenarios.
8. Return lendable face limits and delivery-feasibility certificate, uncertainty, source lineage and a GO/STOP/BLOCKED verdict. Escalate Endogenous cheapest-to-deliver switches, delivery timing rules and fee cancellation terms matter; mark-to-model delivery value is not realized cash profit. Never trade, change contracts, deploy or claim empirical completion from this document alone.

Use PLAN for adapter boundaries and TASKS for traceability; retain immutable manifests and dependency locks when implementation is later authorized. This repository workflow is not installed as a personal ChatGPT skill.
