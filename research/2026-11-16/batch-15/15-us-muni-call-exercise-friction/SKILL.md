---
name: research-us-muni-call-exercise-friction
description: Design or evaluate us municipal call-exercise friction surface for United States tax-exempt callable municipal bonds; use for the stated economic decision, point-in-time data audit, baseline challenge and falsification gates. Research workflow only; not a deployed runtime.
---

# Research US Municipal Call-Exercise Friction Surface

1. State the decision: Choose between matched callable bonds using a calibrated call hazard and cash-flow stress rather than yield-to-worst alone. Read SPEC for `QMG-20261116-15` requirements and EVALS for the frozen gate before selecting a model.
2. Resolve public sources in SOURCES first. Use bond x call opportunity x public notice/financial filing event; reject unlicensed payloads and missing publication times. Preserve observed, published, received, available and effective times separately.
3. Align inputs to this clock: Use only disclosures disseminated by prior close; trade at next obtainable firm offer/bid with a one-session latency. A call notice must enter at publication, not retroactively at the optional call date. Build refunding incentive, notice state, issuer friction and time-to-call. Keep future outcomes and later amendments out of features.
4. Reproduce the baseline: Exercise at first call date when modeled refunding savings exceed a fixed 3% threshold; compare yield-to-worst selection. Match risk, costs, sample, execution clock and permitted actions before testing Discrete-time survival model with economic refunding covariates.
5. Run the domain negative test: Insert a public call notice after the prior-close cutoff: the model must not predict certainty before disclosure. A noncallable bond must have zero optional call hazard. Stop on any future-data acceptance or hard-constraint violation.
6. Challenge the hypothesis: Issuer-friction call probabilities reduce one-year cash-flow forecast error by at least 15% versus deterministic first-economic-call exercise and improve net matched-bond selection by 15 bps per annum. Apply exactly: GO if >=15% cash-flow MAE reduction and >=15 net annualized bps on >=500 held-out call opportunities; STOP if trade-vs-quote bias or missing failed/uncalled bonds explains gains. Report all failed variants and effective independent sample size.
7. Review Illustrative $40m matched-bond sleeve; cap issue ownership and trade size relative to observed turnover, allow days to execute and charge dealer markup. No presumption of instantaneous municipal execution. Recompute the purely illustrative ROI using measured cost evidence if available; otherwise retain the assumption label and negative scenarios.
8. Return call probability surface, cash-flow distribution and duration-matched selection report, uncertainty, source lineage and a GO/STOP/BLOCKED verdict. Escalate Issuer credit, tax law, refunding restrictions and tender/redemption mechanics vary. Trade marks are not executable offers; repeated bonds from one issuer inflate sample size. Never trade, change contracts, deploy or claim empirical completion from this document alone.

Use PLAN for adapter boundaries and TASKS for traceability; retain immutable manifests and dependency locks when implementation is later authorized. This repository workflow is not installed as a personal ChatGPT skill.
