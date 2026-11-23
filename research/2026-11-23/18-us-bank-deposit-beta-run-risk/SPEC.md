# SPEC — US Bank Deposit Beta and Mark-to-Market Securities Run Risk
**B17-18 / Global/domestic quant research; draft specification, approval pending.**

## Problem / use case
Reported uninsured deposits and HTM unrealized losses alone do not measure repricing speed or franchise response.
**Decision:** Assess which banks face funding-cost and securities-loss convexity under uninsured deposit migration.
**H1:** A joint deposit-beta and securities mark-to-market gap predicts earnings/credit deterioration better than uninsured deposit percentage.
**H0:** candidate adds no statistically and economically material value against the feasible baseline after costs and legal/market access controls.

## Mathematics and variables
```text
NII_i≈Loans_i*r_L - Deposits_i*(r_D0+β_i*Δr) - Wholesale_i*r_W ; StressGap_i=HTMLoss_i+RunOutflow_i*FundingSpread
```
β_i deposit repricing elasticity, HTMLoss published held-to-maturity unrealized loss proxy, RunOutflow scenario.
All time indices, units, constraints and payoff signs must be independently checked before a production implementation.

## Data grain / timing
**Required:** FDIC bank Call Reports, quarterly uninsured deposits, HTM/AFS loss fields, benchmark rates, bank equity CDS
**Decision and publication clock:** Quarter-end balances become usable only at the first public Call Report publication, not period end.
Required per source record: `observed_at_utc`, `published_at_utc`, `available_at_utc`, `effective_at_utc`, revision/version ID, legal use class, source proof and missingness marker. Never use postdecision publications or final revised data as historical knowledge.

## Explicit requirements
| Identifier | Requirement and trace |
|---|---|
| REQ-001 | Reconstruct permitted choice for: Assess which banks face funding-cost and securities-loss convexity under uninsured deposit migration. |
| REQ-002 | Baseline on matched opportunity set: Uninsured deposit share plus book capital ratio |
| REQ-003 | Research model: Hierarchical deposit beta estimation plus accounting-based duration stress |
| REQ-004 | Falsify using: Next-quarter NII loss, downside rank precision, capital shortfall, sector-neutral return IC |
| NFR-001 | Deterministic seeds; auditable source, math and version manifest |
| NFR-002 | Fail closed for invalid rights, infeasible choices, conflicts and missing cost inputs |
| AC-001 | Synthetic fixture rejects future information and impossible states (REQ-001,NFR-001) |
| AC-002 | Exact/economically feasible baseline unit tests pass (REQ-002) |
| AC-003 | Candidate and baseline use identical contemporaneously feasible opportunities (REQ-003) |
| AC-004 | Holdout reports uncertainty and net economic downside, without winner-only selection (REQ-004) |
| AC-005 | Legal/publication/capacity controls forbid unauthorized outputs (NFR-002) |

## Scope, risks and stop/go
**Risk:** Quarterly revisions, mergers, bank survivorship and missing bank-specific deposit pricing.
**Stop research if:** No incremental forecast versus capital/deposit mix baseline after strict public release lag.
**Non-goals:** live trade placement, confidential data release, automatic rule interpretation, unsupported empirical returns.
**Economic case (illustrative only):** $155k assumed total 24m development/data/maintenance cost; assumed launch in month 6; assumed annual gross outcome downside/base/upside $0k/$120k/$245k. Resulting 24m net ROI **-100.0% / 16.1% / 137.1% (downside/base/upside)**. These are invented transparent sensitivity inputs, not measured ROI, P&L, or investment advice.
**Evidence status:** no data access, code implementation, tests or paper novelty proof completed.
