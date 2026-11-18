# Specification — US Municipal Call-Exercise Friction Surface

**QMG-20261116-15 · B — Domestic/global quant markets · research design, empirical state BLOCKED.**

## Decision and hypothesis

Choose between matched callable bonds using a calibrated call hazard and cash-flow stress rather than yield-to-worst alone. Issuer-friction call probabilities reduce one-year cash-flow forecast error by at least 15% versus deterministic first-economic-call exercise and improve net matched-bond selection by 15 bps per annum.

```text
P(call_it=1|alive)=logit^-1(alpha+beta*refi_saving_it-gamma*friction_i+delta*notice_state_it); P_i=sum_s P(s|I_t)*sum_tau CF_i,tau(s)*D_t(tau); duration_limit<=K, issuer_weight<=0.05
```

refi_saving is modeled present-value saving using only as-of curves and permitted call terms; friction includes issue size and previously disclosed covenants; notice_state records public call notice; CF scenario cash flows; D discount factors; K duration-risk cap. Tax treatment is a declared investor scenario, not personalized advice.

## Traceable requirements

| ID | Requirement | Objective acceptance |
|---|---|---|
| QMG-20261116-15-REQ-01 | Ingest bond x call opportunity x public notice/financial filing event | Source/version/hash, rights and all time fields present; reject invalid units. |
| QMG-20261116-15-REQ-02 | Build refunding incentive, notice state, issuer friction and time-to-call | Every constituent available_at <= decision_at; no revised-history overwrite. |
| QMG-20261116-15-REQ-03 | Implement baseline: Exercise at first call date when modeled refunding savings exceed a fixed 3% threshold; compare yield-to-worst selection. | Independent deterministic fixture and parity in risk/cost/information. |
| QMG-20261116-15-REQ-04 | Fit/solve Discrete-time survival model with economic refunding covariates | Output hard-constraint certificate and holdout-ready predictions/actions. |
| QMG-20261116-15-REQ-05 | Evaluate call timing distribution, cash-flow forecast error and duration-adjusted bond return | Apply the fixed primary gate below without post-hoc threshold changes. |
| QMG-20261116-15-REQ-06 | Produce call probability surface, cash-flow distribution and duration-matched selection report | Include uncertainty, rejected decisions, cost/capacity and source lineage. |

| ID | Nonfunctional/acceptance requirement |
|---|---|
| QMG-20261116-15-NFR-01 | Every parsed call term needs a document page/span; conflicting extraordinary versus optional redemption clauses block valuation. |
| QMG-20261116-15-NFR-02 | Deterministic seeds, immutable inputs, exact dependency hashes and no network in replay; private adapters disabled by default. |
| QMG-20261116-15-AC-01 | GO if >=15% cash-flow MAE reduction and >=15 net annualized bps on >=500 held-out call opportunities; STOP if trade-vs-quote bias or missing failed/uncalled bonds explains gains. |
| QMG-20261116-15-AC-02 | Insert a public call notice after the prior-close cutoff: the model must not predict certainty before disclosure. A noncallable bond must have zero optional call hazard. |
| QMG-20261116-15-AC-03 | Zero future-input assertions violated; all universe exits retained or explicitly explained; unmatched rights/timestamp rows excluded. |

## Data, economic units and failure semantics

EMMA official statements and public call notices, contemporaneously released issuer financials, trades with dissemination timestamps, call schedules, accrued interest and matched yield curves. Public browsing is not assumed licensed bulk extraction. Clock: Use only disclosures disseminated by prior close; trade at next obtainable firm offer/bid with a one-session latency. A call notice must enter at publication, not retroactively at the optional call date. Distinguish event observation, public dissemination, local receipt and future effective date. Validate native amount, annualized rate, day-count and local currency before USD-equivalent ROI conversion. Missing data do not become zeros; unavailable actions return HOLD/BLOCKED with a reason.

## Risks and economics

Issuer credit, tax law, refunding restrictions and tender/redemption mechanics vary. Trade marks are not executable offers; repeated bonds from one issuer inflate sample size. Illustrative $40m matched-bond sleeve; cap issue ownership and trade size relative to observed turnover, allow days to execute and charge dealer markup. No presumption of instantaneous municipal execution. See [README](README.md) for full illustrative ROI arithmetic and [SOURCES](SOURCES.md) for verified link scope. Publication: High: exercise frictions and segmented fixed income; strong public-document reproducibility potential.
