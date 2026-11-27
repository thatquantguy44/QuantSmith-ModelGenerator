# SPEC — Corporate Bond Securities Lending from CDS Basis Hedge Demand
**B17-02 / Securities finance; draft specification, approval pending.**

## Problem / use case
Bond loan fee and borrow utilization can rise when short-bond/long-CDS trades require physical inventory, but cash-bond liquidity masks causality.
**Decision:** Allocate bond lending supply to CDS-bond basis hedging demand with counterparty and liquidity limits.
**H1:** CDS-bond basis dislocations predict incremental observable bond borrowing demand after conditioning on issue float, liquidity and credit stress.
**H0:** candidate adds no statistically and economically material value against the feasible baseline after costs and legal/market access controls.

## Mathematics and variables
```text
E[BorrowDemand_{i,t+1}|F_t]=f(Basis_{i,t},Float_i,Liquidity_{i,t}); max_q Σ_i q_i*(fee_i - failCost_i) with q_i≤available_i
```
Basis=CDS spread minus matched cash-bond spread; q_i is feasible bond loan notional; borrower behavior must be estimated.
All time indices, units, constraints and payoff signs must be independently checked before a production implementation.

## Data grain / timing
**Required:** CUSIP-level corporate bond lending fees/locates, CDS curves, TRACE trade activity, issue amount, corporate actions
**Decision and publication clock:** CDS and cash-bond spreads only after published executable quote times; lending fills observed subsequently.
Required per source record: `observed_at_utc`, `published_at_utc`, `available_at_utc`, `effective_at_utc`, revision/version ID, legal use class, source proof and missingness marker. Never use postdecision publications or final revised data as historical knowledge.

## Explicit requirements
| Identifier | Requirement and trace |
|---|---|
| REQ-001 | Reconstruct permitted choice for: Allocate bond lending supply to CDS-bond basis hedging demand with counterparty and liquidity limits. |
| REQ-002 | Baseline on matched opportunity set: Trailing borrower request count and issue-size utilization |
| REQ-003 | Research model: Matched event study plus borrow-arrival hazard conditional on CDS-bond basis |
| REQ-004 | Falsify using: Borrow-arrival log score, realized net fee improvement, stale quote rate and borrow supply capacity |
| NFR-001 | Deterministic seeds; auditable source, math and version manifest |
| NFR-002 | Fail closed for invalid rights, infeasible choices, conflicts and missing cost inputs |
| AC-001 | Synthetic fixture rejects future information and impossible states (REQ-001,NFR-001) |
| AC-002 | Exact/economically feasible baseline unit tests pass (REQ-002) |
| AC-003 | Candidate and baseline use identical contemporaneously feasible opportunities (REQ-003) |
| AC-004 | Holdout reports uncertainty and net economic downside, without winner-only selection (REQ-004) |
| AC-005 | Legal/publication/capacity controls forbid unauthorized outputs (NFR-002) |

## Scope, risks and stop/go
**Risk:** Non-executable CDS quotes, bond TRACE delay and endogeneity of credit distress.
**Stop research if:** Estimated basis effects fail paired holdouts or increase rejected locates after slippage and liquidity controls.
**Non-goals:** live trade placement, confidential data release, automatic rule interpretation, unsupported empirical returns.
**Economic case (illustrative only):** $150k assumed total 24m development/data/maintenance cost; assumed launch in month 7; assumed annual gross outcome downside/base/upside $0k/$110k/$230k. Resulting 24m net ROI **-100.0% / 3.9% / 117.2% (downside/base/upside)**. These are invented transparent sensitivity inputs, not measured ROI, P&L, or investment advice.
**Evidence status:** no data access, code implementation, tests or paper novelty proof completed.
