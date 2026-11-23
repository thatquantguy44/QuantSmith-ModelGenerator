# SPEC — Regulatory LCR/NSFR Shadow Cost of Secured Funding Collateral
**B17-10 / Securities finance; draft specification, approval pending.**

## Problem / use case
A cheap repo can be uneconomic when it reduces HQLA or increases required stable funding disproportionately.
**Decision:** Allocate financing transactions by incremental liquidity-ratio headroom consumption, not only nominal repo spread.
**H1:** Dual-priced LCR/NSFR constraints reorder feasible funding selections and improve all-in liquidity-adjusted economics versus spread ranking.
**H0:** candidate adds no statistically and economically material value against the feasible baseline after costs and legal/market access controls.

## Mathematics and variables
```text
min_x Σ_i (r_i*x_i + k_i*x_i) subject to HQLA(x)/NetCashOutflows(x)≥LCR_min and ASF(x)/RSF(x)≥NSFR_min, Σ_i x_i≥Need
```
x_i secured funding quantities, k_i legal balance-sheet charge; LCR, ASF, RSF use approved regulatory definitions.
All time indices, units, constraints and payoff signs must be independently checked before a production implementation.

## Data grain / timing
**Required:** Public Basel ratio methodology/aggregate trends, synthetic collateral classes, cashflow ladder and legal-entity matrices
**Decision and publication clock:** Regulatory rule version, haircut classification and reporting entity apply as of funding decision.
Required per source record: `observed_at_utc`, `published_at_utc`, `available_at_utc`, `effective_at_utc`, revision/version ID, legal use class, source proof and missingness marker. Never use postdecision publications or final revised data as historical knowledge.

## Explicit requirements
| Identifier | Requirement and trace |
|---|---|
| REQ-001 | Reconstruct permitted choice for: Allocate financing transactions by incremental liquidity-ratio headroom consumption, not only nominal repo spread. |
| REQ-002 | Baseline on matched opportunity set: Rank repo offers by quoted rate subject to gross notional limits |
| REQ-003 | Research model: Linear/mixed-integer secured funding allocation with LCR/NSFR dual-price attribution |
| REQ-004 | Falsify using: All-in liquidity-adjusted cost, marginal dual price, buffer breaches, sensitivity to rule version |
| NFR-001 | Deterministic seeds; auditable source, math and version manifest |
| NFR-002 | Fail closed for invalid rights, infeasible choices, conflicts and missing cost inputs |
| AC-001 | Synthetic fixture rejects future information and impossible states (REQ-001,NFR-001) |
| AC-002 | Exact/economically feasible baseline unit tests pass (REQ-002) |
| AC-003 | Candidate and baseline use identical contemporaneously feasible opportunities (REQ-003) |
| AC-004 | Holdout reports uncertainty and net economic downside, without winner-only selection (REQ-004) |
| AC-005 | Legal/publication/capacity controls forbid unauthorized outputs (NFR-002) |

## Scope, risks and stop/go
**Risk:** Entity-specific regulatory implementation and internal forecasts differ; cannot reconstruct actual LCR from public totals.
**Stop research if:** No cost difference over conservative liquidity-constrained benchmark or unstable/uninterpretable duals.
**Non-goals:** live trade placement, confidential data release, automatic rule interpretation, unsupported empirical returns.
**Economic case (illustrative only):** $180k assumed total 24m development/data/maintenance cost; assumed launch in month 8; assumed annual gross outcome downside/base/upside $0k/$120k/$280k. Resulting 24m net ROI **-100.0% / -11.1% / 107.4% (downside/base/upside)**. These are invented transparent sensitivity inputs, not measured ROI, P&L, or investment advice.
**Evidence status:** no data access, code implementation, tests or paper novelty proof completed.
