# Specification — Cross-Border Settlement Calendar Bridge Planner

**QMG-20261116-08 · A — Securities finance · research design, empirical state BLOCKED.**

## Decision and hypothesis

Choose an earlier settlement date and minimal bridge cash for already approved cross-border obligations. A service-specific dated-calendar planner eliminates at least 90% of calendar-caused exceptions and lowers bridge funding cost by 10% versus a fixed two-business-day prefunding rule.

```text
min_b,t sum_j r_j*b_j*d_j/360 + transfer_j + penalty_j*u_j; cash_balance_(c,t)>=0, settlement_open_(service,t)=1, t_j<=deadline_j, bridge_c<=limit_c
```

j obligation; b bridge cash in local currency; d calendar days; r annual funding rate; u unmet obligation indicator; c currency; t chosen settlement instant. USD ROI converts each realized local-currency cost at decision-time hedged FX rates.

## Traceable requirements

| ID | Requirement | Objective acceptance |
|---|---|---|
| QMG-20261116-08-REQ-01 | Ingest obligation leg x settlement service x UTC instant | Source/version/hash, rights and all time fields present; reject invalid units. |
| QMG-20261116-08-REQ-02 | Build service open intervals, version effective dates, cash-day gaps and DST conversion | Every constituent available_at <= decision_at; no revised-history overwrite. |
| QMG-20261116-08-REQ-03 | Implement baseline: Prefund every cross-border obligation two generic business days early, with manual holiday review. | Independent deterministic fixture and parity in risk/cost/information. |
| QMG-20261116-08-REQ-04 | Fit/solve Time-expanded multi-service cash-flow network | Output hard-constraint certificate and holdout-ready predictions/actions. |
| QMG-20261116-08-REQ-05 | Evaluate bridge cash-days and avoidable calendar exceptions | Apply the fixed primary gate below without post-hoc threshold changes. |
| QMG-20261116-08-REQ-06 | Produce prefunding dates, minimal cash bridge and infeasible-leg alerts | Include uncertainty, rejected decisions, cost/capacity and source lineage. |

| ID | Nonfunctional/acceptance requirement |
|---|---|
| QMG-20261116-08-NFR-01 | Timezone-aware UTC storage with local service timezone preserved; unknown calendar version returns BLOCKED, never a guessed weekday. |
| QMG-20261116-08-NFR-02 | Deterministic seeds, immutable inputs, exact dependency hashes and no network in replay; private adapters disabled by default. |
| QMG-20261116-08-AC-01 | GO if >=90% calendar exceptions avoided and >=10% net bridge-cost saving on >=24 holiday windows; zero infeasible settlement recommendations. STOP if routing assumptions require unapproved service access. |
| QMG-20261116-08-AC-02 | Replay US/Europe DST mismatch, Good Friday and a service-specific cutoff extension; the planner must distinguish securities and cash service availability. |
| QMG-20261116-08-AC-03 | Zero future-input assertions violated; all universe exits retained or explicitly explained; unmatched rights/timestamp rows excluded. |

## Data, economic units and failure semantics

Official service calendars and versioned cutoffs, announced closures/extensions, obligation currency/security legs and value dates, available prefunding routes and firm rates. Clock: Plan at least two local business days before a known holiday, using rules announced by then. Unexpected outages are separate stress scenarios; announced future changes enter only after their publication. Distinguish event observation, public dissemination, local receipt and future effective date. Validate native amount, annualized rate, day-count and local currency before USD-equivalent ROI conversion. Missing data do not become zeros; unavailable actions return HOLD/BLOCKED with a reason.

## Risks and economics

Future operating-day changes differ between funds and securities services. DST, half-days and local date conventions can introduce 24-hour errors; a public calendar is not a service entitlement. Illustrative $200m annual recurring bridge balances in USD equivalent; same approved obligations, no new FX carry position. Saving bounded by actual overlap days and bridge rates. See [README](README.md) for full illustrative ROI arithmetic and [SOURCES](SOURCES.md) for verified link scope. Publication: Medium: formal temporal service graph and reproducible operational errors; high practical portability.
