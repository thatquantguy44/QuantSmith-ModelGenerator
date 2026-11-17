# Specification — Australian Water Allocation Shadow Price and Crop Basis

**QMG-20261116-20 · B — Domestic/global quant markets · research design, empirical state BLOCKED.**

## Decision and hypothesis

Choose regional agricultural exposure or a crop-futures hedge only when released water scarcity changes affect a documented crop budget and survive basis costs. Allocation-decision surprises and transfer-constrained water shadow prices improve regional crop-margin forecasts by at least 10% versus seasonal water availability, and reduce hedge downside error by 5% net of costs.

```text
max_(a,w) sum_c crop_price_c*yield_c(w_c)*a_c-water_price*w_c-other_cost_c*a_c; sum_c w_c<=allocation, transfer_flow_z<=limit_z; hedge_h=min E[(margin-h*crop_futures)^2]+k*abs(h)
```

c crop; a planted area; w irrigation water ML; yield response fixed from prior agronomic evidence; allocation released entitlement volume; z transfer zone; h futures hedge units; crop_price and water_price are as-of observations with reporting lags. No physical water trading rights are assumed.

## Traceable requirements

| ID | Requirement | Objective acceptance |
|---|---|---|
| QMG-20261116-20-REQ-01 | Ingest water zone x allocation release x reported trade and crop season | Source/version/hash, rights and all time fields present; reject invalid units. |
| QMG-20261116-20-REQ-02 | Build announced allocation innovation, transfer-zone shadow price and crop-water budget | Every constituent available_at <= decision_at; no revised-history overwrite. |
| QMG-20261116-20-REQ-03 | Implement baseline: Seasonal allocation-volume score with a fixed regional crop basket and constant futures hedge ratio. | Independent deterministic fixture and parity in risk/cost/information. |
| QMG-20261116-20-REQ-04 | Fit/solve Constrained crop-water optimization with allocation-shock local projections | Output hard-constraint certificate and holdout-ready predictions/actions. |
| QMG-20261116-20-REQ-05 | Evaluate regional crop-margin forecast and hedge basis-adjusted downside loss | Apply the fixed primary gate below without post-hoc threshold changes. |
| QMG-20261116-20-REQ-06 | Produce crop-margin scenario, local water shadow price and hedge-basis feasibility verdict | Include uncertainty, rejected decisions, cost/capacity and source lineage. |

| ID | Nonfunctional/acceptance requirement |
|---|---|
| QMG-20261116-20-NFR-01 | Separate entitlement from allocation units and record ML, hectares and currency explicitly; unknown zone connectivity blocks cross-zone flow. |
| QMG-20261116-20-NFR-02 | Deterministic seeds, immutable inputs, exact dependency hashes and no network in replay; private adapters disabled by default. |
| QMG-20261116-20-AC-01 | GO if margin MAE improves >=10% and net hedge downside loss >=5% across >=8 independently held-out seasons/zones; STOP if publication lag eliminates signal or local scarcity has no stable tradable crop exposure. |
| QMG-20261116-20-AC-02 | Give identical aggregate water to two disconnected zones: optimization must retain different shadow prices; delaying trade reporting must move its first eligible feature date. |
| QMG-20261116-20-AC-03 | Zero future-input assertions violated; all universe exits retained or explicitly explained; unmatched rights/timestamp rows excluded. |

## Data, economic units and failure semantics

BOM public allocation decisions and water trades, first-publication/registration timestamps, transfer-zone limits, crop budgets, planting calendars and regional prices; licensed crop futures/basis and official agronomic response data to be resolved. Clock: Update only after verified allocation announcement; water transaction price enters at public reporting time, not settlement/trade date. Trade a hedge no earlier than next liquid session; use seasons as independent split units. Distinguish event observation, public dissemination, local receipt and future effective date. Validate native amount, annualized rate, day-count and local currency before USD-equivalent ROI conversion. Missing data do not become zeros; unavailable actions return HOLD/BLOCKED with a reason.

## Risks and economics

Water rights, allocation trades and permanent entitlements are different assets. Thin reported prices, changing transfer limits and endogenous crop choice can defeat identification; crop futures may be a poor regional hedge. Illustrative $15m agricultural exposure, small research capacity. Limit futures to <=1% lagged volume; water transactions require separate legal/access review and are not assumed executable by the researcher. See [README](README.md) for full illustrative ROI arithmetic and [SOURCES](SOURCES.md) for verified link scope. Publication: High interdisciplinary potential, but weak tradable hedge linkage makes this an intentionally lower-priority contrarian project.
