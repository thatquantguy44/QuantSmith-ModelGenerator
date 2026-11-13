# SPEC — Settlement-Fail Buy-In versus Wait Optimal Stopping
**ID:** QMG-20261113-06 · **Status:** Draft; human approval required · **Category:** A · Securities finance · **Geography:** US Treasury and agency settlement

## Problem and decision
A failed security delivery can become more expensive to cure over time, but immediate market buy-in can also overpay and harm relationships.
**Decision supported:** For an already-failed settlement instruction, decide when to cover, reroute or await delivery under documented close-out rules.

## H1 versus H0
**H1:** A time-to-cure policy using fail penalties and executable cover costs lowers realized failure resolution expense versus fixed escalation cutoffs.
**H0:** A cost-inclusive Auto-escalate after fixed N-day failure age. matches or exceeds the candidate on strictly out-of-sample decisions. The intent is falsification, not confirmation.

## Mathematical problem and domain
```text
V_t(s)=min{cover_cost_t(s), reroute_cost_t(s), fail_penalty_t(s)+E[V_(t+1)(s')|s]}
```
s contains security, counterparty, days failed, available cover liquidity and contractual remedy state.
**Capacity and eligibility:** Limited by available deliverable security and realistic executable cover bids.
Unspecified coefficients must be estimated only from training windows and no undocumented constraint may be relaxed.

## Source, clock and data contract
Public dealer failure aggregates for calibration; synthetic failure life histories; approved buy-in quotes, fails charges and legal remedies. **Observation grain:** failed settlement instruction × elapsed failed day × cut-off timestamp. **Decision horizon:** business-day cure decisions only after confirmed fail and remedy eligibility.
At minimum require `observation_id`, `effective_at`, `published_at`, `available_at`, `ingested_at`, `source_uri`, `license_class`, `revision_id`, `unit`. `available_at <= decision_time` is mandatory for all market signals. New revisions create new records and must not silently overwrite historical decisions.

## Functional and nonfunctional requirements
| ID | Explicit requirement | Priority |
|---|---|---|
| REQ-001 | Model the permitted choice: For an already-failed settlement instruction, decide when to cover, reroute or await delivery under documented close-out rules. | Must |
| REQ-002 | Reproduce feasible benchmark: Auto-escalate after fixed N-day failure age. | Must |
| REQ-003 | Implement candidate Discrete-time survival model with exact dynamic-programming stopping rule. only after benchmark | Must |
| REQ-004 | Report resolved failure days, total cure cost, forced buy-in count, missed deadline, tail loss. and matched capacity/execution economics | Must |
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
USD $130k hypothetical 24-month engineering/data/maintenance cost; gross benefit sensitivity $65k–$260k over 24 months. Net ROI = (gross benefit − cost)/cost = **-50% to 100%**. NOT forecast or historical measurement. Economic lever: scenario: fewer unnecessary emergency cover trades on an illustrative $150m failed notional portfolio over two years.. Source availability: Primary dealer fails are aggregate benchmarks, not individual securities or cost histories.
Funding, transaction cost and execution constraints require separate real calibration.

## Primary risks and negative gates
- **RISK-001:** Fails charges and rights to enforce buy-ins differ by asset, market and contract; wrong assumptions invalidate decisions.
- **RISK-002:** Data sparsity, nonstationarity, multiple testing and selection effects.
- **RISK-003:** Rights, settlement or investability restrictions may make an apparent opportunity infeasible.
- **Predeclared stop:** Reject if holdout cost savings are below 5% or any mandated deadline is missed.
- **Non-goals:** Trading, legal/compliance approvals, publishing real P&L, or deployment from this spec alone.
