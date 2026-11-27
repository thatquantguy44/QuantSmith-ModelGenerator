# SPEC — Securities Loan Retroactive Rate Amendment Revenue Assurance
**B17-04 / Securities finance; draft specification, approval pending.**

## Problem / use case
Backdated fee changes, rate boundaries and returns can create avoidable invoice differences even without a pricing alpha.
**Decision:** Identify contractually unsupported retroactive fee amendments before invoice posting.
**H1:** Bitemporal contract-and-loan event reconstruction detects more true billing exceptions than end-of-day price reconciliation without increasing false disputes.
**H0:** candidate adds no statistically and economically material value against the feasible baseline after costs and legal/market access controls.

## Mathematics and variables
```text
Invoice_i=Σ_{d∈loanlife_i} Principal_{i,d} * Fee_{i,d} * DayFraction_d ; Error_i=Invoice_posted_i-Invoice_authorized_i
```
Fee_i,d is effective authorized fee, distinct from late recorded amendment; Principal is open borrow notional.
All time indices, units, constraints and payoff signs must be independently checked before a production implementation.

## Data grain / timing
**Required:** Synthetic loans, amendment lifecycle, dated fee notices, loan terminations, currency and day-count conventions
**Decision and publication clock:** Invoice run includes only fee amendments authorized and received before invoice cut-off, even if effective date is earlier.
Required per source record: `observed_at_utc`, `published_at_utc`, `available_at_utc`, `effective_at_utc`, revision/version ID, legal use class, source proof and missingness marker. Never use postdecision publications or final revised data as historical knowledge.

## Explicit requirements
| Identifier | Requirement and trace |
|---|---|
| REQ-001 | Reconstruct permitted choice for: Identify contractually unsupported retroactive fee amendments before invoice posting. |
| REQ-002 | Baseline on matched opportunity set: Latest agreed fee × end-period balance × elapsed days |
| REQ-003 | Research model: Bitemporal finite-state rate and loan lifecycle ledger with invariant checks |
| REQ-004 | Falsify using: Synthetic exception precision/recall, manual hours, invoice basis-point leakage, false escalation rate |
| NFR-001 | Deterministic seeds; auditable source, math and version manifest |
| NFR-002 | Fail closed for invalid rights, infeasible choices, conflicts and missing cost inputs |
| AC-001 | Synthetic fixture rejects future information and impossible states (REQ-001,NFR-001) |
| AC-002 | Exact/economically feasible baseline unit tests pass (REQ-002) |
| AC-003 | Candidate and baseline use identical contemporaneously feasible opportunities (REQ-003) |
| AC-004 | Holdout reports uncertainty and net economic downside, without winner-only selection (REQ-004) |
| AC-005 | Legal/publication/capacity controls forbid unauthorized outputs (NFR-002) |

## Scope, risks and stop/go
**Risk:** Contract-level bilateral waiver rules, fee confirmation ambiguity and out-of-order event feeds.
**Stop research if:** No improvement in high-severity seeded exceptions relative to deterministic ledger, or unauthorized dispute actions.
**Non-goals:** live trade placement, confidential data release, automatic rule interpretation, unsupported empirical returns.
**Economic case (illustrative only):** $105k assumed total 24m development/data/maintenance cost; assumed launch in month 4; assumed annual gross outcome downside/base/upside $0k/$95k/$165k. Resulting 24m net ROI **-100.0% / 50.8% / 161.9% (downside/base/upside)**. These are invented transparent sensitivity inputs, not measured ROI, P&L, or investment advice.
**Evidence status:** no data access, code implementation, tests or paper novelty proof completed.
