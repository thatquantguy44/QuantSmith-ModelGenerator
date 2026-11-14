# SPEC — Cross-Book Securities Finance Identity Reconciliation Graph
**ID:** QMG-20261113-10 · **Status:** Draft; human approval required · **Category:** A · Securities finance · **Geography:** US and cross-border securities-finance operations

## Problem and decision
Trade/loan, security and collateral IDs can diverge across booking, servicing and settlement systems, producing false liquidity constraints and duplicated risk.
**Decision supported:** Resolve and quarantine inconsistent identities before financing position, collateral and exposure optimization.

## H1 versus H0
**H1:** A provenance-aware deterministic graph matcher reduces unresolved break hours and false exposure duplications compared with fuzzy string matching.
**H0:** A cost-inclusive Exact ID join plus manually triaged fuzzy-name matches. matches or exceeds the candidate on strictly out-of-sample decisions. The intent is falsification, not confirmation.

## Mathematical problem and domain
```text
min_M Σ_(i,j) c_ij*M_ij + λ*unmatched(M); M_ij∈{0,1}, one-to-one constraints and incompatible identifier rules
```
M_ij selects a candidate match between external and canonical records; c_ij is audited mismatch cost with hard ID prohibitions.
**Capacity and eligibility:** No market capacity required; scalability measured in records/day and audit/log cost, not claimed P&L.
Unspecified coefficients must be estimated only from training windows and no undocumented constraint may be relaxed.

## Source, clock and data contract
Synthetic records containing lifecycle events, ISIN/CUSIP, product type, settlement date, amount, counterparty alias and amendment chain. **Observation grain:** source record × canonical candidate × event version × timestamp. **Decision horizon:** real-time/overnight reconciliation; no future correction can be applied retroactively to a prior risk snapshot.
At minimum require `observation_id`, `effective_at`, `published_at`, `available_at`, `ingested_at`, `source_uri`, `license_class`, `revision_id`, `unit`. `available_at <= decision_time` is mandatory for all market signals. New revisions create new records and must not silently overwrite historical decisions.

## Functional and nonfunctional requirements
| ID | Explicit requirement | Priority |
|---|---|---|
| REQ-001 | Model the permitted choice: Resolve and quarantine inconsistent identities before financing position, collateral and exposure optimization. | Must |
| REQ-002 | Reproduce feasible benchmark: Exact ID join plus manually triaged fuzzy-name matches. | Must |
| REQ-003 | Implement candidate Bipartite deterministic matching with hard identity constraints and provenance. only after benchmark | Must |
| REQ-004 | Report false merge rate, unmatched %, time to resolve, duplicate exposure USD, manual review hours. and matched capacity/execution economics | Must |
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
USD $145k hypothetical 24-month engineering/data/maintenance cost; gross benefit sensitivity $60k–$295k over 24 months. Net ROI = (gross benefit − cost)/cost = **-59% to 103%**. NOT forecast or historical measurement. Economic lever: scenario: 100–500 manual breaks annually at assumed fully loaded remediation costs; purely hypothetical.. Source availability: Official definitions guide field semantics, but real records remain private; publish only synthetic fixtures.
Funding, transaction cost and execution constraints require separate real calibration.

## Primary risks and negative gates
- **RISK-001:** LLM or probabilistic model can silently merge legally distinct entities or settlement legs.
- **RISK-002:** Data sparsity, nonstationarity, multiple testing and selection effects.
- **RISK-003:** Rights, settlement or investability restrictions may make an apparent opportunity infeasible.
- **Predeclared stop:** Reject if critical false merges exceed zero in labeled holdouts or operations time does not decline.
- **Non-goals:** Trading, legal/compliance approvals, publishing real P&L, or deployment from this spec alone.
