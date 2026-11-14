# SPEC — Cash versus Noncash Loan-Collateral Economic Frontier
**ID:** QMG-20261113-07 · **Status:** Draft; human approval required · **Category:** A · Securities finance · **Geography:** US and international agent lending

## Problem and decision
Collateral types impose different rebates, reinvestment limits, liquidity haircuts, indemnification capital and operational expenses, so headline loan fees are not comparable.
**Decision supported:** Price and select borrower-offered collateral methods within owner mandate and agent legal permission.

## H1 versus H0
**H1:** An all-in haircut, rebate and risk-adjusted price frontier improves loan profitability versus fee-only collateral preference.
**H0:** A cost-inclusive Choose the highest headline loan spread among eligible offers. matches or exceeds the candidate on strictly out-of-sample decisions. The intent is falsification, not confirmation.

## Mathematical problem and domain
```text
max_(j∈allowed) [borrow_fee_j + permissible_reinvestment_yield_j - rebate_j - liquidity_cost_j - expected_loss_j - capital_j]
```
j denotes a feasible collateral convention; values must use common horizon and comparable currency-adjusted cash flows.
**Capacity and eligibility:** Constrained by approved collateral classes, reinvestment capacity, borrower credit and liquidity.
Unspecified coefficients must be estimated only from training windows and no undocumented constraint may be relaxed.

## Source, clock and data contract
Cash and noncash terms, rebate schedules, reinvestment constraints, asset eligibility, mark-to-market, haircuts and legal restrictions. **Observation grain:** loan offer × collateral type × owner mandate × quotation timestamp. **Decision horizon:** quote acceptance before loan opening with known collateral terms, not end-of-day realized earnings.
At minimum require `observation_id`, `effective_at`, `published_at`, `available_at`, `ingested_at`, `source_uri`, `license_class`, `revision_id`, `unit`. `available_at <= decision_time` is mandatory for all market signals. New revisions create new records and must not silently overwrite historical decisions.

## Functional and nonfunctional requirements
| ID | Explicit requirement | Priority |
|---|---|---|
| REQ-001 | Model the permitted choice: Price and select borrower-offered collateral methods within owner mandate and agent legal permission. | Must |
| REQ-002 | Reproduce feasible benchmark: Choose the highest headline loan spread among eligible offers. | Must |
| REQ-003 | Implement candidate Loan-specific all-in economic break-even and constraints solver. only after benchmark | Must |
| REQ-004 | Report net economic revenue, risk capital per dollar, haircuts and eligibility breaches, retained lending volume. and matched capacity/execution economics | Must |
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
USD $185k hypothetical 24-month engineering/data/maintenance cost; gross benefit sensitivity $70k–$395k over 24 months. Net ROI = (gross benefit − cost)/cost = **-62% to 114%**. NOT forecast or historical measurement. Economic lever: assume feasible switch of a small subset of a $400m average lending pool at 3–12 bps all-in uplift (unverified).. Source availability: Official repo market rates provide funding context; collateral-type price schedules are program-specific.
Funding, transaction cost and execution constraints require separate real calibration.

## Primary risks and negative gates
- **RISK-001:** Comparing unavailable cash reinvestment yield to executable noncash economics creates phantom spread.
- **RISK-002:** Data sparsity, nonstationarity, multiple testing and selection effects.
- **RISK-003:** Rights, settlement or investability restrictions may make an apparent opportunity infeasible.
- **Predeclared stop:** Reject if no incremental cost-adjusted profit after retaining legally admissible and service-quality constraints.
- **Non-goals:** Trading, legal/compliance approvals, publishing real P&L, or deployment from this spec alone.
