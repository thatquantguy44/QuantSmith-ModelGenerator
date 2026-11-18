# Traceable tasks — Sterling ILTR Auction Demand Smoothing

All research execution tasks are **BLOCKED** in this design-only batch. Documentation completion does not satisfy their definitions of done.

| Task | Traces to | Deliverable / test / definition of done | Blocker |
|---|---|---|---|
| T01 | REQ-01, NFR-02 | Rights-reviewed manifest for auction x collateral set x release version; prove units, source versions and first-public times on a stratified sample. | Source extraction, rights and timestamp audit not performed. |
| T02 | REQ-02, AC-03 | Build clearing-spread intervals, reserve coverage and maturity bucket exposure; test a late amendment, absent source, duplicate version and future-time join. DoD: zero accepted future rows. | T01 and actual as-of module. |
| T03 | REQ-03 | Implement Equal weekly maturities with bids at independently approved maximum willingness-to-pay; compare a single-auction funding plan separately. with independent expected-value fixture and frozen costs/risk. | T01-T02 and baseline implementation. |
| T04 | REQ-04, NFR-01 | Implement Shape-constrained aggregate supply-curve estimation plus stochastic ladder optimization; save feasibility/status, predictions and domain constraints. | T03, dependency lock and solver/model implementation. |
| T05 | AC-02 | Replace the estimated supply curve with a flat curve: the model must not claim auction-price savings from moving a price-taking bid. DoD: expected error/fallback and immutable replay hash. | T02-T04 and synthetic fixture implementation. |
| T06 | REQ-05, AC-01 | Untouched holdout comparison using GBP funding cost, allocation shortfall, maturity concentration, sensitivity to unobserved demand and bridge usage; publish all failed variants and the pre-specified threshold. | Sufficient point-in-time data and T05. |
| T07 | REQ-06 | Measure auction cash-demand ladder with allocation sensitivity bounds; double costs/halve capacity and recompute ROI using actual cost evidence. | T06 and executable/operating cost measurements. |
| T08 | NFR-01, AC-03 | Shadow in a private approved environment; audit manual overrides, constraints and every missing-data event. | Human review, T07 and production data authority. |

Prefix REQ/NFR/AC identifiers with `QMG-20261116-03-` as defined in [SPEC](SPEC.md). No trading, merging or deployment task is authorized by this plan. Human acceptance of a later empirical report is distinct from approving this design PR.
