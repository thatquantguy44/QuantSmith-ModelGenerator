# SPEC — Biotech FDA Catalyst Probability versus Options Event Premium
**B17-16 / Global/domestic quant research; draft specification, approval pending.**

## Problem / use case
Catalyst calendars are susceptible to hindsight because FDA decision timing, clinical surprises and halted quotes interact.
**Decision:** Test whether equity option implied event moves overstate conditional post-decision realized jumps at fixed risk limits.
**H1:** Official pre-event regulatory state improves risk-adjusted event-volatility pricing relative to a generic historical event move.
**H0:** candidate adds no statistically and economically material value against the feasible baseline after costs and legal/market access controls.

## Mathematics and variables
```text
ExpectedJumpVar_i=Σ_s p_{i,s}*(log(P_{after,s}/P_before))^2; VRP_i=ImpliedEventVar_i-ExpectedJumpVar_i-Cost_i
```
s approval/rejection/delay states, p_s probabilities estimated strictly pre-decision; VRP is variance risk premium.
All time indices, units, constraints and payoff signs must be independently checked before a production implementation.

## Data grain / timing
**Required:** FDA event dates, approval histories, pre-event public filings, full options surfaces, equity halt and event-time trades
**Decision and publication clock:** No use of FDA outcome until public approval announcement; option quotes at last feasible pre-event time.
Required per source record: `observed_at_utc`, `published_at_utc`, `available_at_utc`, `effective_at_utc`, revision/version ID, legal use class, source proof and missingness marker. Never use postdecision publications or final revised data as historical knowledge.

## Explicit requirements
| Identifier | Requirement and trace |
|---|---|
| REQ-001 | Reconstruct permitted choice for: Test whether equity option implied event moves overstate conditional post-decision realized jumps at fixed risk limits. |
| REQ-002 | Baseline on matched opportunity set: Historical absolute event returns grouped by market cap and indication |
| REQ-003 | Research model: Regulatory-document event taxonomy + shrinkage conditional jump model |
| REQ-004 | Falsify using: Jump variance calibration, option VRP after costs, event coverage, tail hedge error |
| NFR-001 | Deterministic seeds; auditable source, math and version manifest |
| NFR-002 | Fail closed for invalid rights, infeasible choices, conflicts and missing cost inputs |
| AC-001 | Synthetic fixture rejects future information and impossible states (REQ-001,NFR-001) |
| AC-002 | Exact/economically feasible baseline unit tests pass (REQ-002) |
| AC-003 | Candidate and baseline use identical contemporaneously feasible opportunities (REQ-003) |
| AC-004 | Holdout reports uncertainty and net economic downside, without winner-only selection (REQ-004) |
| AC-005 | Legal/publication/capacity controls forbid unauthorized outputs (NFR-002) |

## Scope, risks and stop/go
**Risk:** FDA database daily updates can lag original approval; sample selection, delistings and halted option quotes.
**Stop research if:** Conditional probability model fails event-matched calibration or net executable option premium.
**Non-goals:** live trade placement, confidential data release, automatic rule interpretation, unsupported empirical returns.
**Economic case (illustrative only):** $195k assumed total 24m development/data/maintenance cost; assumed launch in month 9; assumed annual gross outcome downside/base/upside $0k/$110k/$295k. Resulting 24m net ROI **-100.0% / -29.5% / 89.1% (downside/base/upside)**. These are invented transparent sensitivity inputs, not measured ROI, P&L, or investment advice.
**Evidence status:** no data access, code implementation, tests or paper novelty proof completed.
