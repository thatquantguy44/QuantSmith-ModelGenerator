# SPEC — Arbitrage-Free Equity Volatility Surface Repair Across Markets
**B17-20 / Global/domestic quant research; draft specification, approval pending.**

## Problem / use case
Sparse option quotes violate calendar and butterfly constraints due to stale prices, holidays and different exercise conventions.
**Decision:** Produce arbitrage-consistent option risk surfaces and screen put-call/calendar violations before risk budgeting.
**H1:** Constrained surface repair reduces downstream hedge Greeks error and false arbitrage alarms versus independent spline fitting.
**H0:** candidate adds no statistically and economically material value against the feasible baseline after costs and legal/market access controls.

## Mathematics and variables
```text
min_{σ_surface} Σ_{k,T} w_{k,T}(σ_{k,T}-σ_mid)^2 + λ*Smooth(σ) s.t. ∂_T TotalVar≥0, ConvexCall(K,T)≥0
```
k log-forward moneyness,T maturity; σ implied vol, w quote reliability; bounds depend on option exercise type.
All time indices, units, constraints and payoff signs must be independently checked before a production implementation.

## Data grain / timing
**Required:** Time-synchronized option bid/ask, underlying forwards, dividends, exchange calendars, corporate action adjustments
**Decision and publication clock:** Quote timestamp aligned to each exchange session; repair uses no quotes from future or closed-market snapshots.
Required per source record: `observed_at_utc`, `published_at_utc`, `available_at_utc`, `effective_at_utc`, revision/version ID, legal use class, source proof and missingness marker. Never use postdecision publications or final revised data as historical knowledge.

## Explicit requirements
| Identifier | Requirement and trace |
|---|---|
| REQ-001 | Reconstruct permitted choice for: Produce arbitrage-consistent option risk surfaces and screen put-call/calendar violations before risk budgeting. |
| REQ-002 | Baseline on matched opportunity set: Per-expiry unconstrained cubic interpolation with clip to bid/ask |
| REQ-003 | Research model: Static no-arbitrage SVI/SSVI constrained calibration with conservative quote filters |
| REQ-004 | Falsify using: Static arbitrage violations, held-out option price MAE, hedge delta error, false anomaly alerts |
| NFR-001 | Deterministic seeds; auditable source, math and version manifest |
| NFR-002 | Fail closed for invalid rights, infeasible choices, conflicts and missing cost inputs |
| AC-001 | Synthetic fixture rejects future information and impossible states (REQ-001,NFR-001) |
| AC-002 | Exact/economically feasible baseline unit tests pass (REQ-002) |
| AC-003 | Candidate and baseline use identical contemporaneously feasible opportunities (REQ-003) |
| AC-004 | Holdout reports uncertainty and net economic downside, without winner-only selection (REQ-004) |
| AC-005 | Legal/publication/capacity controls forbid unauthorized outputs (NFR-002) |

## Scope, risks and stop/go
**Risk:** American vs European option styles, dividend marks, early exercise, restricted historical quote rights.
**Stop research if:** Constrained repair does not reduce out-of-sample pricing/hedging error or introduces hidden quote crossings.
**Non-goals:** live trade placement, confidential data release, automatic rule interpretation, unsupported empirical returns.
**Economic case (illustrative only):** $185k assumed total 24m development/data/maintenance cost; assumed launch in month 8; assumed annual gross outcome downside/base/upside $0k/$105k/$265k. Resulting 24m net ROI **-100.0% / -24.3% / 91.0% (downside/base/upside)**. These are invented transparent sensitivity inputs, not measured ROI, P&L, or investment advice.
**Evidence status:** no data access, code implementation, tests or paper novelty proof completed.
