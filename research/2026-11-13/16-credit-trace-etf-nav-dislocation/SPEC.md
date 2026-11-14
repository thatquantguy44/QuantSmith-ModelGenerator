# SPEC — Corporate-Bond TRACE Liquidity-to-ETF NAV Stress Transmission
**ID:** QMG-20261113-16 · **Status:** Draft; human approval required · **Category:** B · Domestic & global markets · **Geography:** United States investment-grade/high-yield credit; optional Europe comparison

## Problem and decision
Bond ETF price-to-NAV discounts may reflect executable underlying liquidity, valuation lag, or hedging demand; naive discounts are not free arbitrage.
**Decision supported:** Hedge credit ETF risk in periods of underlying bond liquidity deterioration without assuming stale NAV is executable.

## H1 versus H0
**H1:** Publication-time TRACE liquidity dispersion predicts subsequent ETF tracking instability beyond ETF realized volatility and HY/IG spread levels.
**H0:** A cost-inclusive ETF realized volatility and quoted bid-ask spread. matches or exceeds the candidate on strictly out-of-sample decisions. The intent is falsification, not confirmation.

## Mathematical problem and domain
```text
LiquidityDisp_t=Q90(trade_cost_bond,t)-Q10(trade_cost_bond,t); predict |ETFprice_t-NAVestimate_t| with quote-timing controls
```
trade_cost_bond is valid time-matched cost proxy; NAVestimate is vendor methodology-specific, potentially stale and never treated as fillable.
**Capacity and eligibility:** Only liquid ETFs and hedges, no synthetic bond execution assuming NAV arbitrage.
Unspecified coefficients must be estimated only from training windows and no undocumented constraint may be relaxed.

## Source, clock and data contract
FINRA TRACE public aggregate/trade pages, subscription historical bond records, ETF market prices, NAV timestamps, bond indices, CDX basis. **Observation grain:** bond × disseminated trade timestamp × ETF NAV publication timestamp. **Decision horizon:** end-of-session / next-session ETF risk adjustment only; public aggregate data may not cover security-level historical panel.
At minimum require `observation_id`, `effective_at`, `published_at`, `available_at`, `ingested_at`, `source_uri`, `license_class`, `revision_id`, `unit`. `available_at <= decision_time` is mandatory for all market signals. New revisions create new records and must not silently overwrite historical decisions.

## Functional and nonfunctional requirements
| ID | Explicit requirement | Priority |
|---|---|---|
| REQ-001 | Model the permitted choice: Hedge credit ETF risk in periods of underlying bond liquidity deterioration without assuming stale NAV is executable. | Must |
| REQ-002 | Reproduce feasible benchmark: ETF realized volatility and quoted bid-ask spread. | Must |
| REQ-003 | Implement candidate Robust bond-liquidity dispersion index and ETF tracking-state model. only after benchmark | Must |
| REQ-004 | Report tracking error forecast, credit tail loss, hedge slippage, redemption-state calibration. and matched capacity/execution economics | Must |
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
USD $215k hypothetical 24-month engineering/data/maintenance cost; gross benefit sensitivity $0k–$455k over 24 months. Net ROI = (gross benefit − cost)/cost = **-100% to 112%**. NOT forecast or historical measurement. Economic lever: hypothetical $20m credit hedge program, saving a fraction of tracking-loss during rare liquidity events; no realized estimate.. Source availability: FINRA explains TRACE reporting and offers public aggregates; institutional historical tick panels may require subscription.
Funding, transaction cost and execution constraints require separate real calibration.

## Primary risks and negative gates
- **RISK-001:** Reported bond prices may be size-capped/delayed; TRACE trade access/licensing varies and NAV can embed stale marks.
- **RISK-002:** Data sparsity, nonstationarity, multiple testing and selection effects.
- **RISK-003:** Rights, settlement or investability restrictions may make an apparent opportunity infeasible.
- **Predeclared stop:** Reject if no incremental tracking error forecast or lower stress drawdown after NAV timestamp normalization and realistic ETF costs.
- **Non-goals:** Trading, legal/compliance approvals, publishing real P&L, or deployment from this spec alone.
