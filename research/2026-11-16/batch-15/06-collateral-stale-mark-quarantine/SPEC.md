# Specification — Collateral Stale-Mark Quarantine and Conservative Valuation

**QMG-20261116-06 · A — Securities finance · research design, empirical state BLOCKED.**

## Decision and hypothesis

Quarantine a suspect mark or assign a conservative valuation interval, escalating exceptions rather than automatically altering contractual marks. A cross-source temporal-consistency gate reduces unsecured-value underestimation by at least 30% versus last-price carry-forward at an operational false-quarantine rate below 1%.

```text
V_i^safe=q_i*L_i*(1-h_i); flag_i=1{age_i>a_i or abs(p_i-p_i^ref)>tau_i}; choose thresholds (a,tau) to minimize E[undersecured_loss]+review_cost subject to P(p_i>=L_i|I_t)>=0.99 and false_quarantine<=0.01
```

q quantity; h haircut; L,U independently calibrated price interval; p_ref lag-safe cross-source reference; age time since valid quote; a maximum age; tau asset-specific tolerance, both fitted on training data; I_t available source information. Quarantined marks cannot create funding capacity. This is a conservative monitoring valuation, not an unauthorized contract valuation.

## Traceable requirements

| ID | Requirement | Objective acceptance |
|---|---|---|
| QMG-20261116-06-REQ-01 | Ingest collateral instrument x mark source x quote/receive event | Source/version/hash, rights and all time fields present; reject invalid units. |
| QMG-20261116-06-REQ-02 | Build source age, price convention residual, lineage overlap and conservative interval | Every constituent available_at <= decision_at; no revised-history overwrite. |
| QMG-20261116-06-REQ-03 | Implement baseline: Use latest received price within a fixed one-day age limit; otherwise last valid mark with static buffer. | Independent deterministic fixture and parity in risk/cost/information. |
| QMG-20261116-06-REQ-04 | Fit/solve Robust cross-source median and asset-specific age/interval rule | Output hard-constraint certificate and holdout-ready predictions/actions. |
| QMG-20261116-06-REQ-05 | Evaluate underestimated unsecured exposure and false quarantine burden | Apply the fixed primary gate below without post-hoc threshold changes. |
| QMG-20261116-06-REQ-06 | Produce mark status, safe monitoring valuation, lineage warning and escalation reason | Include uncertainty, rejected decisions, cost/capacity and source lineage. |

| ID | Nonfunctional/acceptance requirement |
|---|---|
| QMG-20261116-06-NFR-01 | Target p99 <=100ms per 1,000-mark batch excluding upstream network; missing currency/convention hard-fails. Keep original marks immutable. |
| QMG-20261116-06-NFR-02 | Deterministic seeds, immutable inputs, exact dependency hashes and no network in replay; private adapters disabled by default. |
| QMG-20261116-06-AC-01 | GO if underestimation falls >=30%, clean-mark false quarantine <1%, and lower-bound coverage >=99% in stress replay; reject if benefit comes only from excessive haircuts or review burden exceeds 0.5 FTE per 10k instruments. |
| QMG-20261116-06-AC-02 | Inject a 100x currency/unit error, stale timestamp, ex-coupon drop and two nominally independent marks with identical upstream provenance; detect unit/staleness defects while preserving valid convention changes. |
| QMG-20261116-06-AC-03 | Zero future-input assertions violated; all universe exits retained or explicitly explained; unmatched rights/timestamp rows excluded. |

## Data, economic units and failure semantics

Raw vendor price/event/receive timestamps, currency, clean/dirty convention, coupon accrual, corporate actions, independent quote source and later adjudicated corrections. Public rates and eligible-asset terms support synthetic scenarios, not intraday bond valuation. Clock: Gate each mark at ingestion before its use in a financing solve; reference marks must be received earlier than the current solve. Labels are adjudications collected later and assigned only to future model training windows. Distinguish event observation, public dissemination, local receipt and future effective date. Validate native amount, annualized rate, day-count and local currency before USD-equivalent ROI conversion. Missing data do not become zeros; unavailable actions return HOLD/BLOCKED with a reason.

## Risks and economics

Independent sources can share the same vendor lineage. Corporate actions and currency factors can look like outliers; later corrections create hindsight labels. Illustrative $1bn monitored collateral; benefits are operational hours and conservatively estimated error-loss avoidance, not additive lending alpha. Conservative marks can reduce usable funding capacity. See [README](README.md) for full illustrative ROI arithmetic and [SOURCES](SOURCES.md) for verified link scope. Publication: Medium: reproducible error taxonomy and dependence-aware coverage; strongest value may be operational rather than journal novelty.
