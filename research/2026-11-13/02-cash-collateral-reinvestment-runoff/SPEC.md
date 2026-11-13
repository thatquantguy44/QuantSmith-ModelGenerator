# SPEC — Cash-Collateral Reinvestment Liquidity Run-Off Controller
**ID:** QMG-20261113-02 · **Status:** Draft; human approval required · **Category:** A · Securities finance · **Geography:** US securities lending programs

## Problem and decision
Cash collateral received on securities loans can fund instruments whose maturity profile does not match sudden loan returns or borrower collateral recalls.
**Decision supported:** Allocate cash-collateral reinvestment across liquid buckets and pre-fund potential return obligations without sacrificing contractually required safety.

## H1 versus H0
**H1:** State-dependent loan run-off and reinvestment ladder simulation lowers liquidity shortfall probability versus static maturity and expected-return assumptions.
**H0:** A cost-inclusive Static liquidity buffer plus duration/weighted average life constraints. matches or exceeds the candidate on strictly out-of-sample decisions. The intent is falsification, not confirmation.

## Mathematical problem and domain
```text
min_w E[funding_cost(w)+liquidity_shortfall_penalty(w)] + λ CVaR_99(shortfall(w)); Σ_k w_k=1; WAM/WAL/eligibility and liquidity floors hold
```
w_k is share in maturity/liquidity bucket k; CVaR_99 is 99% expected shortfall on repayment funding deficits, not investment P&L.
**Capacity and eligibility:** Capital is constrained by contractual permissible instruments, concentration, tenor limits and financing market depth.
Unspecified coefficients must be estimated only from training windows and no undocumented constraint may be relaxed.

## Source, clock and data contract
Loan termination flows; collateral principal; reinvestment settlement and maturity ladders; redemption windows; eligible funds; short-term yields; stress scenarios. **Observation grain:** cash collateral program × reinvestment maturity bucket × business day. **Decision horizon:** end-of-day reinvestment decision with availability of prior published cash flow and eligible settlement windows.
At minimum require `observation_id`, `effective_at`, `published_at`, `available_at`, `ingested_at`, `source_uri`, `license_class`, `revision_id`, `unit`. `available_at <= decision_time` is mandatory for all market signals. New revisions create new records and must not silently overwrite historical decisions.

## Functional and nonfunctional requirements
| ID | Explicit requirement | Priority |
|---|---|---|
| REQ-001 | Model the permitted choice: Allocate cash-collateral reinvestment across liquid buckets and pre-fund potential return obligations without sacrificing contractually required safety. | Must |
| REQ-002 | Reproduce feasible benchmark: Static liquidity buffer plus duration/weighted average life constraints. | Must |
| REQ-003 | Implement candidate Conditional run-off survival model combined with stochastic cash-flow gap optimizer. only after benchmark | Must |
| REQ-004 | Report 99% liquidity shortfall, reinvestment net yield, liquidity carry, stressed liquidations, breach count. and matched capacity/execution economics | Must |
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
USD $190k hypothetical 24-month engineering/data/maintenance cost; gross benefit sensitivity $80k–$390k over 24 months. Net ROI = (gross benefit − cost)/cost = **-58% to 105%**. NOT forecast or historical measurement. Economic lever: hypothetical $600m collateral pool; avoid 1–5 days of emergency liquidity costs in a 24-month horizon; benefits depend on realized stress frequencies.. Source availability: Public SOFR and money-market rates can proxy the reinvestment curve, not private lending redemption behavior.
Funding, transaction cost and execution constraints require separate real calibration.

## Primary risks and negative gates
- **RISK-001:** Return flows may cluster under crises; survivorship of reinvestment balances causes understated withdrawals.
- **RISK-002:** Data sparsity, nonstationarity, multiple testing and selection effects.
- **RISK-003:** Rights, settlement or investability restrictions may make an apparent opportunity infeasible.
- **Predeclared stop:** Reject if stress shortfalls are not reduced by at least 10% without degrading contractual yield or creating maturity breaches.
- **Non-goals:** Trading, legal/compliance approvals, publishing real P&L, or deployment from this spec alone.
