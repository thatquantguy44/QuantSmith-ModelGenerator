# SPEC — Treasury Clearing Access-Path & Duplicate-Margin Optimizer
**ID:** QMG-20261113-01 · **Status:** Draft; human approval required · **Category:** A · Securities finance · **Geography:** United States; cleared cash Treasury and repo

## Problem and decision
Direct, sponsored and agent clearing routes may impose different netting, margin, liquidity and access costs; a lower repo rate can still be a more expensive end-to-end financing route.
**Decision supported:** Route eligible Treasury financing activity among legally permitted clearing access paths and participant entities while honoring CCP and customer-protection constraints.

## H1 versus H0
**H1:** Path-aware margin, clearing fees and funding costs change the optimal routing mix and reduce total economically consumed liquidity relative to selecting the lowest quoted repo rate.
**H0:** A cost-inclusive Minimize executable repo rate ignoring path-specific costs, after validating that every route is eligible. matches or exceeds the candidate on strictly out-of-sample decisions. The intent is falsification, not confirmation.

## Mathematical problem and domain
```text
min_(x_p) Σ_p x_p*(rate_p*notional*T + fee_p + margin_carry_p + default_fund_p + cclf_liquidity_p) - verified_netting_benefit(x); Σ_p x_p=1; x_p=0 for ineligible paths
```
x_p is fraction routed through path p; T is year-fraction tenor; margin, default fund, CCLF and netting effects use validated path-specific rules rather than assumed offsets.
**Capacity and eligibility:** Constrained by FICC participant access, available repo quote depth, account/entity eligibility and netting-set segregation.
Unspecified coefficients must be estimated only from training windows and no undocumented constraint may be relaxed.

## Source, clock and data contract
Eligible trade templates; path availability; historical quote spreads; initial/variation margin stress; capital/CCLF allocation; modeled netting sets; direct/sponsored/agent fees. **Observation grain:** trade × eligible clearing access path × decision timestamp. **Decision horizon:** trade routing decision at quote acceptance; historical public aggregates are lagged and cannot be used as intraday quotes.
At minimum require `observation_id`, `effective_at`, `published_at`, `available_at`, `ingested_at`, `source_uri`, `license_class`, `revision_id`, `unit`. `available_at <= decision_time` is mandatory for all market signals. New revisions create new records and must not silently overwrite historical decisions.

## Functional and nonfunctional requirements
| ID | Explicit requirement | Priority |
|---|---|---|
| REQ-001 | Model the permitted choice: Route eligible Treasury financing activity among legally permitted clearing access paths and participant entities while honoring CCP and customer-protection constraints. | Must |
| REQ-002 | Reproduce feasible benchmark: Minimize executable repo rate ignoring path-specific costs, after validating that every route is eligible. | Must |
| REQ-003 | Implement candidate Mixed-integer convex routing with separate margin, settlement and liquidity shadow prices. only after benchmark | Must |
| REQ-004 | Report USD all-in funding cost, dollar liquidity encumbrance, margin stress p99, ineligible route count, rejection rate. and matched capacity/execution economics | Must |
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
USD $280k hypothetical 24-month engineering/data/maintenance cost; gross benefit sensitivity $160k–$620k over 24 months. Net ROI = (gross benefit − cost)/cost = **-43% to 121%**. NOT forecast or historical measurement. Economic lever: assume 2–8 bps avoidable total cost on an eligible hypothetical $250m continuously financed at ~1yr equivalent and fraction of volume attainable; capture model must account for actual turnover.. Source availability: SEC and DTCC rules describe access but do not provide participant-specific margin or allocation cost.
Funding, transaction cost and execution constraints require separate real calibration.

## Primary risks and negative gates
- **RISK-001:** Clearing rule exemptions and netting eligibility vary; estimated margin offsets could be nonportable across entities.
- **RISK-002:** Data sparsity, nonstationarity, multiple testing and selection effects.
- **RISK-003:** Rights, settlement or investability restrictions may make an apparent opportunity infeasible.
- **Predeclared stop:** Reject if simulated net savings are below 2 bps of affected financing notional or vanish under independently validated margin rules.
- **Non-goals:** Trading, legal/compliance approvals, publishing real P&L, or deployment from this spec alone.
