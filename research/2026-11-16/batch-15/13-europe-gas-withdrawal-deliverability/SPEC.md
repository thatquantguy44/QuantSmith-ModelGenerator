# Specification — European Gas Storage Deliverability Hedge

**QMG-20261116-13 · B — Domestic/global quant markets · research design, empirical state BLOCKED.**

## Decision and hypothesis

Hedge winter peak gas-delivery risk using facility-level withdrawal constraints rather than national percent-full alone. A deliverability-weighted storage index reduces winter peak procurement CVaR by at least 10% versus a percent-full rule at equal average hedge cost.

```text
min_(u,s) sum_t pi_t*s_t; sum_i u_it+s_t>=D_t, 0<=u_it<=g_i(S_it), S_i,t+1=S_it+injection_it-u_it, 0<=S_it<=capacity_i, pipe_flow<=pipe_capacity; hedge=min_h E[cost(h)] + lambda*CVaR_95(cost(h)), |h|<=H
```

S inventory in MWh; u withdrawal MWh/day; g inventory-dependent deliverability; s shortage MWh; D stressed delivered demand; pi shortage penalty per MWh; i facility; t gas day; injection is an exogenous scenario flow; h hub futures/seasonal spread hedge; H risk/participation cap. Physical flows obey hub connectivity and pipe limits; physical optimization informs shortage exposure, not a claim of storage operating rights.

## Traceable requirements

| ID | Requirement | Objective acceptance |
|---|---|---|
| QMG-20261116-13-REQ-01 | Ingest storage facility x gas day x publication version | Source/version/hash, rights and all time fields present; reject invalid units. |
| QMG-20261116-13-REQ-02 | Build withdrawal headroom, gas-day inventory state and hub connectivity | Every constituent available_at <= decision_at; no revised-history overwrite. |
| QMG-20261116-13-REQ-03 | Implement baseline: Hedge ratio proportional to national percent-full deficit relative to trailing seasonal average. | Independent deterministic fixture and parity in risk/cost/information. |
| QMG-20261116-13-REQ-04 | Fit/solve Constrained physical storage network and linear hedge projection | Output hard-constraint certificate and holdout-ready predictions/actions. |
| QMG-20261116-13-REQ-05 | Evaluate winter peak procurement tail cost and deliverable MWh shortfall | Apply the fixed primary gate below without post-hoc threshold changes. |
| QMG-20261116-13-REQ-06 | Produce deliverability risk index and constrained seasonal hedge weights | Include uncertainty, rejected decisions, cost/capacity and source lineage. |

| ID | Nonfunctional/acceptance requirement |
|---|---|
| QMG-20261116-13-NFR-01 | Use gas-day definitions and MWh conversion consistently; data-quality flags propagate to bounds instead of becoming zero inventory. |
| QMG-20261116-13-NFR-02 | Deterministic seeds, immutable inputs, exact dependency hashes and no network in replay; private adapters disabled by default. |
| QMG-20261116-13-AC-01 | GO if >=10% CVaR reduction at equal mean cost across >=5 winters including one held-out stressed winter; STOP if results reverse under plausible deliverability curves or cross-border restrictions. |
| QMG-20261116-13-AC-02 | Create two facilities with identical percent-full and different withdrawal limits: shortage outputs must differ. Remove one interconnector and forbid unphysical gas flows. |
| QMG-20261116-13-AC-03 | Zero future-input assertions violated; all universe exits retained or explicitly explained; unmatched rights/timestamp rows excluded. |

## Data, economic units and failure semantics

GIE published facility stocks/capacities/data-quality flags, publication versions, hub connectivity and outage notices; inventory-dependent performance curves need validated operator data or explicitly bounded assumptions. Licensed day-ahead/futures curves for hedging. Clock: Recompute after first verified daily publication; execute next liquid hub session with at least one-day lag when historical publication time is unknown. Revised storage values never replace first-release features. Distinguish event observation, public dissemination, local receipt and future effective date. Validate native amount, annualized rate, day-count and local currency before USD-equivalent ROI conversion. Missing data do not become zeros; unavailable actions return HOLD/BLOCKED with a reason.

## Risks and economics

Reported maximum withdrawal is not necessarily sustainable at low fill. Regional bottlenecks and revisions dominate; proxy futures do not deliver facility access. Illustrative $30m annual hedge exposure; use <=1% lagged hub/spread volume and explicit spread liquidity. USD ROI translates net EUR procurement savings at hedged rates; no assumed storage ownership. See [README](README.md) for full illustrative ROI arithmetic and [SOURCES](SOURCES.md) for verified link scope. Publication: High: physical deliverability versus headline inventory; falsifiable nonlinear constraints rather than another weather predictor.
