# SPEC — Dynamic Currency-Hedge and Rebalancing Tax for Global Equity
**ID:** QMG-20261113-19 · **Status:** Draft; human approval required · **Category:** B · Domestic & global markets · **Geography:** US, Japan, euro area, UK and selected liquid EM equity markets

## Problem and decision
Static FX hedges can overpay forward carry, turnover and correlation opportunity costs when equity/FX correlations flip across stress regimes.
**Decision supported:** Allocate country equity exposures and currency forward hedge ratios jointly under leverage, country, counterparty and capital-control constraints.

## H1 versus H0
**H1:** State-adaptive hedging reduces after-cost drawdown without sacrificing a pre-specified return floor relative to 0%, 50% and 100% static hedges.
**H0:** A cost-inclusive 50% static currency hedges plus equal-risk country weights and quarterly turnover. matches or exceeds the candidate on strictly out-of-sample decisions. The intent is falsification, not confirmation.

## Mathematical problem and domain
```text
min_(w,h) E[(R_equity(w)+R_FX(w,h)-target)^2] + λ*ES_95 + μ*turnover(w,h); 0≤h_c≤hmax_c
```
w are country equity weights; h_c hedge fractions; ES_95 is expected shortfall; forward carry and bid/ask are charged at actual roll.
**Capacity and eligibility:** Limit to index futures/ETFs and deliverable/non-deliverable forward liquidity; enforce market access and capital controls.
Unspecified coefficients must be estimated only from training windows and no undocumented constraint may be relaxed.

## Source, clock and data contract
Country index total returns, currency spot/forward curves, FX liquidity, investability restrictions and funding rates. **Observation grain:** country equity market × FX forward tenor × monthly rebalance date. **Decision horizon:** rebalance at scheduled month-end using prior-close prices and then-available forward quotes.
At minimum require `observation_id`, `effective_at`, `published_at`, `available_at`, `ingested_at`, `source_uri`, `license_class`, `revision_id`, `unit`. `available_at <= decision_time` is mandatory for all market signals. New revisions create new records and must not silently overwrite historical decisions.

## Functional and nonfunctional requirements
| ID | Explicit requirement | Priority |
|---|---|---|
| REQ-001 | Model the permitted choice: Allocate country equity exposures and currency forward hedge ratios jointly under leverage, country, counterparty and capital-control constraints. | Must |
| REQ-002 | Reproduce feasible benchmark: 50% static currency hedges plus equal-risk country weights and quarterly turnover. | Must |
| REQ-003 | Implement candidate Robust covariance and transaction-cost-aware FX hedge optimizer. only after benchmark | Must |
| REQ-004 | Report after-cost drawdown, lower-tail CVaR, rolling correlation, FX hedge turnover and volatility. and matched capacity/execution economics | Must |
| NFR-001 | Deterministic fixture replay, point-in-time lineage and seed/config pinning | Must |
| NFR-002 | Confidentiality, access/market eligibility, source licensing and manual review | Must |

## Acceptance criteria
| ID | Covers | Testable requirement |
|---|---|---|
| AC-001 | REQ-001,NFR-001 | Reject unavailable source vintages and impossible decision clocks |
| AC-002 | REQ-002 | Synthetic benchmark passes unit, cost and eligibility invariants |
| AC-003 | REQ-003 | Candidate uses same opportunities/cost rules; reproducible paired holdout |
| AC-004 | REQ-004 | Net economic metrics, intervals, sensitivity and capacity displayed |
| AC-005 | NFR-002 | Public output blocks private rows and unresolved authorization |

## Research economics
USD $135k hypothetical 24-month engineering/data/maintenance cost; gross benefit sensitivity $20k–$270k over 24 months. Net ROI = (gross benefit − cost)/cost = **-85% to 100%**. NOT forecast or historical measurement. Economic lever: hypothetical $30m equity exposure; 0–42 bps annually saved from hedge inefficiency and drawdown control; weak scenario still pays some operational value.. Source availability: MSCI publishes methodology, not unrestricted total return/constituent history; FX and rates data may have licensing restrictions.
Funding, transaction cost and execution constraints require separate real calibration.

## Primary risks and negative gates
- **RISK-001:** Country index histories have vendor survivorship and free-float methodological changes; FX pricing may be unavailable at allocated size.
- **RISK-002:** Data sparsity, nonstationarity, multiple testing and selection effects.
- **RISK-003:** Rights, settlement or investability restrictions may make an apparent opportunity infeasible.
- **Predeclared stop:** Reject if lower-tail risk not improved by at least 5% net of forward carry and turnover without violating return floor.
- **Non-goals:** Trading, legal/compliance approvals, publishing real P&L, or deployment from this spec alone.
