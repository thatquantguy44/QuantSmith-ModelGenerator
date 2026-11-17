# Specification — ECB Collateral Eligibility-Cliff Prepositioning

**QMG-20261116-02 · A — Securities finance · research design, empirical state BLOCKED.**

## Decision and hypothesis

Preposition replacement assets before an announced effective date while charging carry, haircut and transfer costs. A versioned effective-date planner lowers replacement expense by at least 2 annualized basis points on affected balances versus replacing at the deadline, with no use of information before announcement.

```text
min_y sum_(i,t) (carry_it*y_it + transfer_it*abs(y_it-y_i,t-1)) + lambda*CVaR_95(shortfall); sum_i P_it*(1-h_it)*y_it>=L_t, 0<=y_it<=I_it, y_it=0 if E_it=0
```

i indexes assets; t future business dates; y is pledged quantity; P is as-of scenario price; h is effective haircut; L required secured value; I eligible inventory; E is eligibility known or announced at decision time; lambda prices shortfall risk.

## Traceable requirements

| ID | Requirement | Objective acceptance |
|---|---|---|
| QMG-20261116-02-REQ-01 | Ingest ISIN x release version x effective date | Source/version/hash, rights and all time fields present; reject invalid units. |
| QMG-20261116-02-REQ-02 | Build announced future eligibility matrix, haircut-adjusted coverage and replacement ladder | Every constituent available_at <= decision_at; no revised-history overwrite. |
| QMG-20261116-02-REQ-03 | Implement baseline: Replace only at maturity or first effective ineligibility date using cheapest currently eligible asset. | Independent deterministic fixture and parity in risk/cost/information. |
| QMG-20261116-02-REQ-04 | Fit/solve Rolling-horizon linear allocation using announced eligibility transitions | Output hard-constraint certificate and holdout-ready predictions/actions. |
| QMG-20261116-02-REQ-05 | Evaluate replacement implementation cost and eligible-value shortfall | Apply the fixed primary gate below without post-hoc threshold changes. |
| QMG-20261116-02-REQ-06 | Produce dated replacement schedule and coverage stress certificate | Include uncertainty, rejected decisions, cost/capacity and source lineage. |

| ID | Nonfunctional/acceptance requirement |
|---|---|
| QMG-20261116-02-NFR-01 | Preserve source byte hashes and schema versions; reject any unknown CHANGE code or missing effective date instead of guessing. |
| QMG-20261116-02-NFR-02 | Deterministic seeds, immutable inputs, exact dependency hashes and no network in replay; private adapters disabled by default. |
| QMG-20261116-02-AC-01 | GO if cost saving >=2 annualized bps on affected balances and zero eligibility violations across >=20 independent transition clusters; worst stress shortfall no larger than baseline. STOP if timestamp-safe sample is inadequate or cost rises under doubled bid/ask. |
| QMG-20261116-02-AC-02 | Move an announcement after the decision timestamp: all corresponding anticipatory trades must disappear; maturity may remain predictable from previously published terms. |
| QMG-20261116-02-AC-03 | Zero future-input assertions violated; all universe exits retained or explicitly explained; unmatched rights/timestamp rows excluded. |

## Data, economic units and failure semantics

ECB full/delta eligibility files, announcement timestamps, effective dates, maturity, haircuts, issuer mapping, replacement prices and settlement windows. Do not infer a future delisting from a later archive snapshot. Clock: Evaluate after verified ECB publication and ingestion, with a minimum 30-minute operational latency; any action is next eligible settlement window. Historical daily snapshots without timestamp proof are usable only with a conservative next-business-day decision lag. Distinguish event observation, public dissemination, local receipt and future effective date. Validate native amount, annualized rate, day-count and local currency before USD-equivalent ROI conversion. Missing data do not become zeros; unavailable actions return HOLD/BLOCKED with a reason.

## Risks and economics

Current eligibility is not historical eligibility; rating changes may be anticipated in prices. Framework eligibility does not establish institution-specific usability, own-use treatment or transfer rights. Illustrative EUR500m affected annual balances, converted to USD equivalent for ROI. Limited by replacement-asset depth, settlement access and concentration limits; use <=1% observed daily turnover until calibrated. See [README](README.md) for full illustrative ROI arithmetic and [SOURCES](SOURCES.md) for verified link scope. Publication: Medium-high: event-time collateral option value, with public framework changes and transparent effective-time tests.
