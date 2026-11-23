# SPEC — OPEC Oil Balance Residuals and Refined Crack-Spread Transmission
**B17-19 / Global/domestic quant research; draft specification, approval pending.**

## Problem / use case
Production announcements are not physical barrels; apparent balance discrepancies may reflect reporting lags and revision practices.
**Decision:** Hedge product crack spreads when public crude production and stock-flow residuals imply inventory stress.
**H1:** JODI stock-flow residuals after publication improve future refined crack-spread risk forecasts over oil price and seasonal inventories.
**H0:** candidate adds no statistically and economically material value against the feasible baseline after costs and legal/market access controls.

## Mathematics and variables
```text
Residual_{c,m}=Production+Imports-Exports-RefineryIntake-ΔStocks-OtherUse; Crack_t=P_product_t-ConversionRatio*P_crude_t
```
c country,m reporting month; residual is diagnostic with units normalized; price conversion reflects barrel yields.
All time indices, units, constraints and payoff signs must be independently checked before a production implementation.

## Data grain / timing
**Required:** JODI monthly crude stocks/flows, OPEC reports, EIA refinery/product balances, crack-futures settlements
**Decision and publication clock:** JODI typically publishes next-month and revises; align release date, not reporting month; execute only after release.
Required per source record: `observed_at_utc`, `published_at_utc`, `available_at_utc`, `effective_at_utc`, revision/version ID, legal use class, source proof and missingness marker. Never use postdecision publications or final revised data as historical knowledge.

## Explicit requirements
| Identifier | Requirement and trace |
|---|---|
| REQ-001 | Reconstruct permitted choice for: Hedge product crack spreads when public crude production and stock-flow residuals imply inventory stress. |
| REQ-002 | Baseline on matched opportunity set: Seasonal EIA weekly inventories and oil curve |
| REQ-003 | Research model: Constrained oil balance reconciliation and local-projection crack spread model |
| REQ-004 | Falsify using: Out-of-sample crack variance forecast, economic hedge cost, stock-balance residual stability |
| NFR-001 | Deterministic seeds; auditable source, math and version manifest |
| NFR-002 | Fail closed for invalid rights, infeasible choices, conflicts and missing cost inputs |
| AC-001 | Synthetic fixture rejects future information and impossible states (REQ-001,NFR-001) |
| AC-002 | Exact/economically feasible baseline unit tests pass (REQ-002) |
| AC-003 | Candidate and baseline use identical contemporaneously feasible opportunities (REQ-003) |
| AC-004 | Holdout reports uncertainty and net economic downside, without winner-only selection (REQ-004) |
| AC-005 | Legal/publication/capacity controls forbid unauthorized outputs (NFR-002) |

## Scope, risks and stop/go
**Risk:** Monthly country submission corrections, unit conversion mismatches and sanctioned flow missingness.
**Stop research if:** Residual predictive content disappears after vintages, shipping lags and front-month liquidity adjustment.
**Non-goals:** live trade placement, confidential data release, automatic rule interpretation, unsupported empirical returns.
**Economic case (illustrative only):** $170k assumed total 24m development/data/maintenance cost; assumed launch in month 7; assumed annual gross outcome downside/base/upside $0k/$115k/$280k. Resulting 24m net ROI **-100.0% / -4.2% / 133.3% (downside/base/upside)**. These are invented transparent sensitivity inputs, not measured ROI, P&L, or investment advice.
**Evidence status:** no data access, code implementation, tests or paper novelty proof completed.
