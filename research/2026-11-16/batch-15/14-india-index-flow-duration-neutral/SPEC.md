# Specification — India Bond Index-Flow Saturation

**QMG-20261116-14 · B — Domestic/global quant markets · research design, empirical state BLOCKED.**

## Decision and hypothesis

Tilt duration-neutral eligible-versus-near-eligible government bond baskets using dated projected passive demand and realized foreign-flow saturation. Expected demand scaled by free-float turnover predicts inclusion-window residual returns better than an inclusion dummy, and improves net basket return by at least 20 bps per annum.

```text
flow_pressure_it=AUM_known_t*delta_weight_announced_it/free_float_it; R_it=alpha_i+time_t+beta*flow_pressure_it+gamma*ownership_saturation_it+epsilon_it; sum w=0, DV01'w=0, |w_i|<=cap_i
```

AUM_known is a publicly disclosed or licensed contemporaneous index-tracking AUM estimate; delta_weight is announced effective change; free_float excludes known nontrading holders; ownership_saturation uses released ownership/flow data only; w bond positions. Unknown AUM is bounded, never backfilled from later estimates.

## Traceable requirements

| ID | Requirement | Objective acceptance |
|---|---|---|
| QMG-20261116-14-REQ-01 | Ingest government bond x announcement/rebalance cohort x public flow release | Source/version/hash, rights and all time fields present; reject invalid units. |
| QMG-20261116-14-REQ-02 | Build announced flow pressure, free-float turnover and lagged foreign ownership saturation | Every constituent available_at <= decision_at; no revised-history overwrite. |
| QMG-20261116-14-REQ-03 | Implement baseline: Equal-risk inclusion-event basket versus duration-matched eligible controls. | Independent deterministic fixture and parity in risk/cost/information. |
| QMG-20261116-14-REQ-04 | Fit/solve Matched staggered event study with demand-pressure interactions | Output hard-constraint certificate and holdout-ready predictions/actions. |
| QMG-20261116-14-REQ-05 | Evaluate 20-session inclusion-window residual return and diminishing impact at high ownership | Apply the fixed primary gate below without post-hoc threshold changes. |
| QMG-20261116-14-REQ-06 | Produce event-study estimands, placebo diagnostics and duration-neutral research basket | Include uncertainty, rejected decisions, cost/capacity and source lineage. |

| ID | Nonfunctional/acceptance requirement |
|---|---|
| QMG-20261116-14-NFR-01 | Announced and effective membership must occupy separate columns; unknown original announcement time blocks that cohort. |
| QMG-20261116-14-NFR-02 | Deterministic seeds, immutable inputs, exact dependency hashes and no network in replay; private adapters disabled by default. |
| QMG-20261116-14-AC-01 | GO if >=20 net annualized bps improvement and event-cluster confidence lower bound >0; pretrends must pass a specified +/-10 bp equivalence band. STOP if fewer than 3 independent cohorts or ownership/AUM histories are reconstructed retrospectively. |
| QMG-20261116-14-AC-02 | Assign the same event to noneligible placebo bonds and to dates six months earlier; no persistent significant effect should survive cohort-level multiple-testing adjustment. |
| QMG-20261116-14-AC-03 | Zero future-input assertions violated; all universe exits retained or explicitly explained; unmatched rights/timestamp rows excluded. |

## Data, economic units and failure semantics

RBI FAR/public market context, dated index-provider inclusion/weight notices, foreign ownership/flows, bond eligibility, free-float and issue cash flows; local executable price and hedge history. Clock: Act next Mumbai session after a verified inclusion announcement or ownership release; close at a predeclared post-effective window. Never use final index weights or future ownership before announcement. Distinguish event observation, public dissemination, local receipt and future effective date. Validate native amount, annualized rate, day-count and local currency before USD-equivalent ROI conversion. Missing data do not become zeros; unavailable actions return HOLD/BLOCKED with a reason.

## Risks and economics

Eligibility correlates with liquidity and issuance; parallel trends may fail. Single historical inclusion episodes cannot support strong causal or scalable trading claims. Illustrative $50m duration-neutral basket, capped at 1% issue turnover with market access and FX hedging charged. Passive flow estimates are not executable demand guarantees. See [README](README.md) for full illustrative ROI arithmetic and [SOURCES](SOURCES.md) for verified link scope. Publication: High identification interest; scarcity of independent cohorts could make a bounds/survey paper more credible than a causal alpha claim.
