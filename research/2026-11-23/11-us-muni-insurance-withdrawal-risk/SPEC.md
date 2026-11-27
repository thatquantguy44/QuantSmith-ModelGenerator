# SPEC — US Municipal Credit Vulnerability to Local Insurance Withdrawal
**B17-11 / Global/domestic quant research; draft specification, approval pending.**

## Problem / use case
Tax-base deterioration from insurance affordability may be a forward municipal credit risk not captured by standard debt ratios.
**Decision:** Prioritize municipal-credit surveillance and pricing by property tax base sensitivity to insurance availability.
**H1:** Hazard exposure × insurance withdrawal proxies predict later tax-roll stress/spread changes beyond debt-service coverage and demographics.
**H0:** candidate adds no statistically and economically material value against the feasible baseline after costs and legal/market access controls.

## Mathematics and variables
```text
ΔCreditSpread_{c,t+h}=β*(Hazard_c×InsuranceShock_{c,t})+γ'X_{c,t}+μ_c+τ_t+ε
```
c is issuer county/service area, h forward horizon; InsuranceShock uses published insurer exit/premium information.
All time indices, units, constraints and payoff signs must be independently checked before a production implementation.

## Data grain / timing
**Required:** County FEMA risk, EMMA issuer disclosures, municipal price quotes, property valuations, insurer exit/public rate filings
**Decision and publication clock:** County/issuer boundary vintage and disclosure posting timestamp; FEMA risk version frozen at decision date.
Required per source record: `observed_at_utc`, `published_at_utc`, `available_at_utc`, `effective_at_utc`, revision/version ID, legal use class, source proof and missingness marker. Never use postdecision publications or final revised data as historical knowledge.

## Explicit requirements
| Identifier | Requirement and trace |
|---|---|
| REQ-001 | Reconstruct permitted choice for: Prioritize municipal-credit surveillance and pricing by property tax base sensitivity to insurance availability. |
| REQ-002 | Baseline on matched opportunity set: Debt-to-revenue and issuer-rating-only spread screen |
| REQ-003 | Research model: Geospatial panel DiD with insurance availability shock and issuer boundary crosswalk |
| REQ-004 | Falsify using: Out-of-sample spread rank IC, change in tax revenue, false alerts, distress recall |
| NFR-001 | Deterministic seeds; auditable source, math and version manifest |
| NFR-002 | Fail closed for invalid rights, infeasible choices, conflicts and missing cost inputs |
| AC-001 | Synthetic fixture rejects future information and impossible states (REQ-001,NFR-001) |
| AC-002 | Exact/economically feasible baseline unit tests pass (REQ-002) |
| AC-003 | Candidate and baseline use identical contemporaneously feasible opportunities (REQ-003) |
| AC-004 | Holdout reports uncertainty and net economic downside, without winner-only selection (REQ-004) |
| AC-005 | Legal/publication/capacity controls forbid unauthorized outputs (NFR-002) |

## Scope, risks and stop/go
**Risk:** FEMA risk baseline old; climate model not equivalent to observed insurance withdrawal; selective municipal disclosure.
**Stop research if:** No incremental out-of-time predictive effect after socioeconomic covariates and issuer-selection controls.
**Non-goals:** live trade placement, confidential data release, automatic rule interpretation, unsupported empirical returns.
**Economic case (illustrative only):** $160k assumed total 24m development/data/maintenance cost; assumed launch in month 7; assumed annual gross outcome downside/base/upside $0k/$100k/$260k. Resulting 24m net ROI **-100.0% / -11.5% / 130.2% (downside/base/upside)**. These are invented transparent sensitivity inputs, not measured ROI, P&L, or investment advice.
**Evidence status:** no data access, code implementation, tests or paper novelty proof completed.
