# SPEC — Agency MBS Dollar-Roll Cheapest-to-Deliver Financing Option
**B17-01 / Securities finance; draft specification, approval pending.**

## Problem / use case
TBA rolls embed delivery-option value; treating the drop as a pure financing rate may underprice pool selection and settlement frictions.
**Decision:** Select TBA dollar-roll financing and permissible pool delivery sets versus holding specified pools financed through repo.
**H1:** Explicit deliverability and pool opportunity costs explain dollar-roll implied funding differences beyond coupon, term and simple financing spreads.
**H0:** candidate adds no statistically and economically material value against the feasible baseline after costs and legal/market access controls.

## Mathematics and variables
```text
min_{x_p in {0,1}} Σ_p x_p*(PoolCarry_p + DeliveryCost_p - RollDrop_p), subject to Σ_p x_p = DeliverableNotional, Eligible_p=1
```
x_p is assigned pool fraction/selection, RollDrop is dollar-roll price drop, Eligible_p delivery eligibility; preserve coupon/payup units.
All time indices, units, constraints and payoff signs must be independently checked before a production implementation.

## Data grain / timing
**Required:** TBA front/back prices, pools, payups, coupon schedules, specified-pool risk, MBSD netting, EPN eligibility and execution costs
**Decision and publication clock:** Decision at pre-roll executable quote; EPN pool assignment becomes known later and must not leak into earlier signals.
Required per source record: `observed_at_utc`, `published_at_utc`, `available_at_utc`, `effective_at_utc`, revision/version ID, legal use class, source proof and missingness marker. Never use postdecision publications or final revised data as historical knowledge.

## Explicit requirements
| Identifier | Requirement and trace |
|---|---|
| REQ-001 | Reconstruct permitted choice for: Select TBA dollar-roll financing and permissible pool delivery sets versus holding specified pools financed through repo. |
| REQ-002 | Baseline on matched opportunity set: Dollar-roll implied financing vs same-tenor generic repo without delivery-option valuation |
| REQ-003 | Research model: Constrained pool-delivery optimizer with observable pool financing carry and roll prices |
| REQ-004 | Falsify using: Net financing bps, cheapest-deliverable premium, pre-settlement fail exposure, netted capital and tail regret |
| NFR-001 | Deterministic seeds; auditable source, math and version manifest |
| NFR-002 | Fail closed for invalid rights, infeasible choices, conflicts and missing cost inputs |
| AC-001 | Synthetic fixture rejects future information and impossible states (REQ-001,NFR-001) |
| AC-002 | Exact/economically feasible baseline unit tests pass (REQ-002) |
| AC-003 | Candidate and baseline use identical contemporaneously feasible opportunities (REQ-003) |
| AC-004 | Holdout reports uncertainty and net economic downside, without winner-only selection (REQ-004) |
| AC-005 | Legal/publication/capacity controls forbid unauthorized outputs (NFR-002) |

## Scope, risks and stop/go
**Risk:** Pool price selection, payup optionality, actual pool availability and post-trade EPN leakage.
**Stop research if:** No stable out-of-sample cost-adjusted advantage over delivery-aware manual baseline at realistic pool eligibility.
**Non-goals:** live trade placement, confidential data release, automatic rule interpretation, unsupported empirical returns.
**Economic case (illustrative only):** $180k assumed total 24m development/data/maintenance cost; assumed launch in month 6; assumed annual gross outcome downside/base/upside $0k/$130k/$260k. Resulting 24m net ROI **-100.0% / 8.3% / 116.7% (downside/base/upside)**. These are invented transparent sensitivity inputs, not measured ROI, P&L, or investment advice.
**Evidence status:** no data access, code implementation, tests or paper novelty proof completed.
