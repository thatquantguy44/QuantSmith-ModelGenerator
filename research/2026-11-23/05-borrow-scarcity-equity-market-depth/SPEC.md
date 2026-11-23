# SPEC — Borrow Scarcity Causal Effect on Equity Market-Maker Quoted Depth
**B17-05 / Securities finance; draft specification, approval pending.**

## Problem / use case
Borrow fee spikes coincide with volatility and funding stress; ordinary cross-sectional regressions confuse cause and effect.
**Decision:** Adjust financing risk capital for equity liquidity provision when short-sale borrow becomes scarce.
**H1:** Exogenous changes to borrow supply lower subsequent displayed depth/increase effective spreads more than matched control stocks.
**H0:** candidate adds no statistically and economically material value against the feasible baseline after costs and legal/market access controls.

## Mathematics and variables
```text
Depth_{i,t}=α_i+δ_t+β*BorrowSupplyShock_{i,t}+γ'X_{i,t}+ε_{i,t}; H0: β=0
```
BorrowSupplyShock is preannounced/exogenous eligible inventory change; X contains liquidity and issuer controls.
All time indices, units, constraints and payoff signs must be independently checked before a production implementation.

## Data grain / timing
**Required:** Borrow availability and fees, market quotes/trades, issuer event calendars and exclusion instruments
**Decision and publication clock:** Quote-decision timing after actual supply notice; event timestamps distinguish pre-event leak, regular session and close.
Required per source record: `observed_at_utc`, `published_at_utc`, `available_at_utc`, `effective_at_utc`, revision/version ID, legal use class, source proof and missingness marker. Never use postdecision publications or final revised data as historical knowledge.

## Explicit requirements
| Identifier | Requirement and trace |
|---|---|
| REQ-001 | Reconstruct permitted choice for: Adjust financing risk capital for equity liquidity provision when short-sale borrow becomes scarce. |
| REQ-002 | Baseline on matched opportunity set: Spread/depth forecasting using only realized volatility and market cap |
| REQ-003 | Research model: Matched differences-in-differences/event-time instrumental analysis |
| REQ-004 | Falsify using: Event-time β confidence interval, placebos, effective spread, depth and incremental risk price |
| NFR-001 | Deterministic seeds; auditable source, math and version manifest |
| NFR-002 | Fail closed for invalid rights, infeasible choices, conflicts and missing cost inputs |
| AC-001 | Synthetic fixture rejects future information and impossible states (REQ-001,NFR-001) |
| AC-002 | Exact/economically feasible baseline unit tests pass (REQ-002) |
| AC-003 | Candidate and baseline use identical contemporaneously feasible opportunities (REQ-003) |
| AC-004 | Holdout reports uncertainty and net economic downside, without winner-only selection (REQ-004) |
| AC-005 | Legal/publication/capacity controls forbid unauthorized outputs (NFR-002) |

## Scope, risks and stop/go
**Risk:** Selection on distressed shorts, simultaneous volatility and hard-to-borrow endogenous events.
**Stop research if:** No pre-registered effect with valid pretrends/instruments or effect only on illiquid untradeable names.
**Non-goals:** live trade placement, confidential data release, automatic rule interpretation, unsupported empirical returns.
**Economic case (illustrative only):** $220k assumed total 24m development/data/maintenance cost; assumed launch in month 9; assumed annual gross outcome downside/base/upside $0k/$120k/$310k. Resulting 24m net ROI **-100.0% / -31.8% / 76.1% (downside/base/upside)**. These are invented transparent sensitivity inputs, not measured ROI, P&L, or investment advice.
**Evidence status:** no data access, code implementation, tests or paper novelty proof completed.
