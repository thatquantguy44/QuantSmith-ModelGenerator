# SPEC — Repo Coupon and Principal Event Cash-Flow Netting Scheduler
**B17-03 / Securities finance; draft specification, approval pending.**

## Problem / use case
Security cash-flow dates and bilateral payment terms can create avoidable gross cash movements even when net exposure is small.
**Decision:** Minimize same-day cash deficits caused by collateral coupon/principal flows and contractual manufactured payments.
**H1:** Event-aware legally permissible netting reduces liquidity buffer and operational exceptions versus cash-flow-independent settlement.
**H0:** candidate adds no statistically and economically material value against the feasible baseline after costs and legal/market access controls.

## Mathematics and variables
```text
min_{f_{ij,t},B_t} Σ_t (c_B*B_t+c_F*|f_t|) s.t. Cash_t + B_t + inflow_t - outflow_t ≥0; NettingSet_{ij}=1
```
f_ij,t are settlement payment flows; B_t is funding buffer; NettingSet is legal contractual binary.
All time indices, units, constraints and payoff signs must be independently checked before a production implementation.

## Data grain / timing
**Required:** Public bond schedules, ex-coupon dates, settlement calendars, synthetic counterparties and netting agreements
**Decision and publication clock:** Coupon schedule published at issuance; adjustments and confirmed obligations only after contract notice timestamp.
Required per source record: `observed_at_utc`, `published_at_utc`, `available_at_utc`, `effective_at_utc`, revision/version ID, legal use class, source proof and missingness marker. Never use postdecision publications or final revised data as historical knowledge.

## Explicit requirements
| Identifier | Requirement and trace |
|---|---|
| REQ-001 | Reconstruct permitted choice for: Minimize same-day cash deficits caused by collateral coupon/principal flows and contractual manufactured payments. |
| REQ-002 | Baseline on matched opportunity set: Gross independent payment processing with static buffer |
| REQ-003 | Research model: Mixed-integer liquidity scheduling with eligibility/netting-set constraints |
| REQ-004 | Falsify using: Peak cash buffer, gross payment count, exception cost, settlement timeliness |
| NFR-001 | Deterministic seeds; auditable source, math and version manifest |
| NFR-002 | Fail closed for invalid rights, infeasible choices, conflicts and missing cost inputs |
| AC-001 | Synthetic fixture rejects future information and impossible states (REQ-001,NFR-001) |
| AC-002 | Exact/economically feasible baseline unit tests pass (REQ-002) |
| AC-003 | Candidate and baseline use identical contemporaneously feasible opportunities (REQ-003) |
| AC-004 | Holdout reports uncertainty and net economic downside, without winner-only selection (REQ-004) |
| AC-005 | Legal/publication/capacity controls forbid unauthorized outputs (NFR-002) |

## Scope, risks and stop/go
**Risk:** Wrong beneficial-ownership treatment, netting rights and special cash settlement terms.
**Stop research if:** No capacity-adjusted cost reduction versus pre-netted conventional operations or violations of payment rights.
**Non-goals:** live trade placement, confidential data release, automatic rule interpretation, unsupported empirical returns.
**Economic case (illustrative only):** $120k assumed total 24m development/data/maintenance cost; assumed launch in month 5; assumed annual gross outcome downside/base/upside $0k/$95k/$190k. Resulting 24m net ROI **-100.0% / 25.3% / 150.7% (downside/base/upside)**. These are invented transparent sensitivity inputs, not measured ROI, P&L, or investment advice.
**Evidence status:** no data access, code implementation, tests or paper novelty proof completed.
