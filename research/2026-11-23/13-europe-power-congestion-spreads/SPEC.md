# SPEC — European Interconnector Congestion Power-Spread State Estimator
**B17-13 / Global/domestic quant research; draft specification, approval pending.**

## Problem / use case
Observed day-ahead power spread contains congestion rents, bidding-zone rules and renewable shocks; unconstrained price regressions overstate arbitrage.
**Decision:** Select hedged cross-zone power spread exposures conditional on public transfer constraints.
**H1:** Transmission-capacity-corrected congestion states improve next-day risk classification and hedge calibration versus load-only spread models.
**H0:** candidate adds no statistically and economically material value against the feasible baseline after costs and legal/market access controls.

## Mathematics and variables
```text
Spread_{a,b,t}=Price_a,t-Price_b,t; Flow_{ab,t}≤ATC_{ab,t}; max_q E[q*Spread-CongestionCost(q)] with |q|≤AccessCap
```
a,b bidding zones; ATC available transfer capacity; q a hypothetical permitted hedge, not a physically available arbitrage.
All time indices, units, constraints and payoff signs must be independently checked before a production implementation.

## Data grain / timing
**Required:** ENTSO-E day-ahead prices, transfer capacities, interconnector outages, wind/load forecasts and contract liquidity
**Decision and publication clock:** Only ENTSO-E forecasts published before day-ahead bidding deadline; actual flows/prices are evaluation targets.
Required per source record: `observed_at_utc`, `published_at_utc`, `available_at_utc`, `effective_at_utc`, revision/version ID, legal use class, source proof and missingness marker. Never use postdecision publications or final revised data as historical knowledge.

## Explicit requirements
| Identifier | Requirement and trace |
|---|---|
| REQ-001 | Reconstruct permitted choice for: Select hedged cross-zone power spread exposures conditional on public transfer constraints. |
| REQ-002 | Baseline on matched opportunity set: Historical seasonal hourly spread by zone pair |
| REQ-003 | Research model: Physical-congestion regime HMM with capacity-constrained exposure mapper |
| REQ-004 | Falsify using: Congestion regime Brier score, spread MAE, feasible net hedge carry and stress CVaR |
| NFR-001 | Deterministic seeds; auditable source, math and version manifest |
| NFR-002 | Fail closed for invalid rights, infeasible choices, conflicts and missing cost inputs |
| AC-001 | Synthetic fixture rejects future information and impossible states (REQ-001,NFR-001) |
| AC-002 | Exact/economically feasible baseline unit tests pass (REQ-002) |
| AC-003 | Candidate and baseline use identical contemporaneously feasible opportunities (REQ-003) |
| AC-004 | Holdout reports uncertainty and net economic downside, without winner-only selection (REQ-004) |
| AC-005 | Legal/publication/capacity controls forbid unauthorized outputs (NFR-002) |

## Scope, risks and stop/go
**Risk:** Cross-zone transmission rights and operational capacities not freely tradable; timestamps and price revisions.
**Stop research if:** Spread gains disappear after simultaneous public forecast access, congestion settlement and capacity rights.
**Non-goals:** live trade placement, confidential data release, automatic rule interpretation, unsupported empirical returns.
**Economic case (illustrative only):** $220k assumed total 24m development/data/maintenance cost; assumed launch in month 9; assumed annual gross outcome downside/base/upside $0k/$150k/$355k. Resulting 24m net ROI **-100.0% / -14.8% / 101.7% (downside/base/upside)**. These are invented transparent sensitivity inputs, not measured ROI, P&L, or investment advice.
**Evidence status:** no data access, code implementation, tests or paper novelty proof completed.
