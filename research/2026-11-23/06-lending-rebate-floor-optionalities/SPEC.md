# SPEC — Securities Lending Cash Rebate Floor Optionality in Low-Rate Regimes
**B17-06 / Securities finance; draft specification, approval pending.**

## Problem / use case
Minimum rebate or fee floors make effective funding convex at negative short rates; a linear spread assumption can misstate value.
**Decision:** Price and hedge rebate-floor optionality embedded in cash-collateral loan agreements.
**H1:** Contract-aware nonlinear floor valuation reduces forecast carry error and improper pricing vs linear spread assumptions.
**H0:** candidate adds no statistically and economically material value against the feasible baseline after costs and legal/market access controls.

## Mathematics and variables
```text
PV_floor=E^Q[Σ_t DF_t*CashCollateral_t*max(K-r_t,0)*Δt]; Revenue=baseFee+PV_floor-hedgeCost
```
K is contractual rebate floor, r_t relevant overnight collateral rate, DF discount factor, Δt year fraction.
All time indices, units, constraints and payoff signs must be independently checked before a production implementation.

## Data grain / timing
**Required:** Historical overnight benchmarks, collateral currency curves, cash balances, contract rebate-floor clauses
**Decision and publication clock:** Valuation at contract initiation using curve observed by quote cut-off, not future realized policy rates.
Required per source record: `observed_at_utc`, `published_at_utc`, `available_at_utc`, `effective_at_utc`, revision/version ID, legal use class, source proof and missingness marker. Never use postdecision publications or final revised data as historical knowledge.

## Explicit requirements
| Identifier | Requirement and trace |
|---|---|
| REQ-001 | Reconstruct permitted choice for: Price and hedge rebate-floor optionality embedded in cash-collateral loan agreements. |
| REQ-002 | Baseline on matched opportunity set: Static contractual rebate minus benchmark with no optionality |
| REQ-003 | Research model: Rate-tree floor valuation and curve calibration with contract clause parser |
| REQ-004 | Falsify using: Pricing replication error, stress carry, calibration error and limit-breach count |
| NFR-001 | Deterministic seeds; auditable source, math and version manifest |
| NFR-002 | Fail closed for invalid rights, infeasible choices, conflicts and missing cost inputs |
| AC-001 | Synthetic fixture rejects future information and impossible states (REQ-001,NFR-001) |
| AC-002 | Exact/economically feasible baseline unit tests pass (REQ-002) |
| AC-003 | Candidate and baseline use identical contemporaneously feasible opportunities (REQ-003) |
| AC-004 | Holdout reports uncertainty and net economic downside, without winner-only selection (REQ-004) |
| AC-005 | Legal/publication/capacity controls forbid unauthorized outputs (NFR-002) |

## Scope, risks and stop/go
**Risk:** Floor rights and term structures vary by legal agreement; historic negative-rate regimes have sample limitations.
**Stop research if:** Valuation adds no meaningful incremental pricing accuracy to conservative quoted-fee schedules.
**Non-goals:** live trade placement, confidential data release, automatic rule interpretation, unsupported empirical returns.
**Economic case (illustrative only):** $135k assumed total 24m development/data/maintenance cost; assumed launch in month 7; assumed annual gross outcome downside/base/upside $0k/$80k/$225k. Resulting 24m net ROI **-100.0% / -16.0% / 136.1% (downside/base/upside)**. These are invented transparent sensitivity inputs, not measured ROI, P&L, or investment advice.
**Evidence status:** no data access, code implementation, tests or paper novelty proof completed.
