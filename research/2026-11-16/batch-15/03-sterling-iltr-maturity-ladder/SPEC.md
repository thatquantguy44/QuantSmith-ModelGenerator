# Specification — Sterling ILTR Auction Demand Smoothing

**QMG-20261116-03 · A — Securities finance · research design, empirical state BLOCKED.**

## Decision and hypothesis

Distribute a fixed eligible reserve requirement across future ILTR auctions and collateral sets without assuming a strategic low bid improves the clearing price. Demand smoothing lowers all-in expected funding expense by at least 1 bp relative to a single-auction ladder while preserving liquidity coverage under adverse allocation outcomes.

```text
min_q sum_(a,c) E[s_ac(Q_a)*q_ac]*T_a/365 + bridge_cost(q); sum_(a,c) q_ac*1{a settles<=t<a matures}>=L_t, sum_a q_ac<=C_c, q_ac>=0
```

a is auction; c collateral set; q is requested GBP cash; s is clearing spread as a function of aggregate demand Q; T tenor days; L reserve requirement; C haircut-adjusted eligible collateral. Bids are bounded by independently estimated willingness-to-pay; no assumed access to competitor bids.

## Traceable requirements

| ID | Requirement | Objective acceptance |
|---|---|---|
| QMG-20261116-03-REQ-01 | Ingest auction x collateral set x release version | Source/version/hash, rights and all time fields present; reject invalid units. |
| QMG-20261116-03-REQ-02 | Build clearing-spread intervals, reserve coverage and maturity bucket exposure | Every constituent available_at <= decision_at; no revised-history overwrite. |
| QMG-20261116-03-REQ-03 | Implement baseline: Equal weekly maturities with bids at independently approved maximum willingness-to-pay; compare a single-auction funding plan separately. | Independent deterministic fixture and parity in risk/cost/information. |
| QMG-20261116-03-REQ-04 | Fit/solve Shape-constrained aggregate supply-curve estimation plus stochastic ladder optimization | Output hard-constraint certificate and holdout-ready predictions/actions. |
| QMG-20261116-03-REQ-05 | Evaluate cost of a reserve maturity ladder subject to stressed coverage | Apply the fixed primary gate below without post-hoc threshold changes. |
| QMG-20261116-03-REQ-06 | Produce auction cash-demand ladder with allocation sensitivity bounds | Include uncertainty, rejected decisions, cost/capacity and source lineage. |

| ID | Nonfunctional/acceptance requirement |
|---|---|
| QMG-20261116-03-NFR-01 | Every schedule uses Europe/London DST and verified effective facility calibration; missing auction rule version blocks recommendation. |
| QMG-20261116-03-NFR-02 | Deterministic seeds, immutable inputs, exact dependency hashes and no network in replay; private adapters disabled by default. |
| QMG-20261116-03-AC-01 | GO if >=1 bp net annualized saving versus equal ladder in >=12 held-out operations and no stressed reserve shortfall. STOP if all plausible demand curves imply the same ladder or savings require underbidding actual willingness-to-pay. |
| QMG-20261116-03-AC-02 | Replace the estimated supply curve with a flat curve: the model must not claim auction-price savings from moving a price-taking bid. |
| QMG-20261116-03-AC-03 | Zero future-input assertions violated; all universe exits retained or explicitly explained; unmatched rights/timestamp rows excluded. |

## Data, economic units and failure semantics

Published BoE operation results, facility rules, publication timestamps, collateral-set spreads and tenors; simulated reserve paths; licensed GBP alternative-funding quotes for later testing. Clock: Use results only after public release; plan by 09:00 Europe/London before an operation using earlier operations and latest approved reserve forecast. Verify each current auction deadline before a live pilot. Distinguish event observation, public dissemination, local receipt and future effective date. Validate native amount, annualized rate, day-count and local currency before USD-equivalent ROI conversion. Missing data do not become zeros; unavailable actions return HOLD/BLOCKED with a reason.

## Risks and economics

Aggregate clearing outcomes do not identify individual demand or fill probabilities. Facility calibration changes can invalidate extrapolation; official participation rules take precedence. Illustrative GBP500m reserve need in USD-equivalent ROI; size must be small relative to auction capacity or explicitly model own impact. Operational access, collateral prepositioning and bridge-funding limits bind. See [README](README.md) for full illustrative ROI arithmetic and [SOURCES](SOURCES.md) for verified link scope. Publication: High identification interest, conditional on transparent partial-identification bounds rather than a falsely recovered demand curve.
