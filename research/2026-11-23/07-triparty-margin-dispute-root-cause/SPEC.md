# SPEC — Tri-Party Repo Margin Dispute Root-Cause and Evidence Classifier
**B17-07 / Securities finance; draft specification, approval pending.**

## Problem / use case
Operational margin disputes are often triaged from unstructured tickets without reconstructing mark, haircut and event timing.
**Decision:** Resolve margin disagreements by independently identifying stale marks, eligibility mismatches and cut-off conventions.
**H1:** A deterministic calculation engine plus provenance graph resolves more disputes correctly than keyword-based ticket routing.
**H0:** candidate adds no statistically and economically material value against the feasible baseline after costs and legal/market access controls.

## Mathematics and variables
```text
DisputeAmount_j=Σ_i (Mark_{i,t}*(1-h_i)*Qty_i)_bank - Σ_i (Mark_{i,t}*(1-h_i)*Qty_i)_agent
```
h_i haircut and Mark_i mark at contractual timestamp; compare sides only when valuation basis matches.
All time indices, units, constraints and payoff signs must be independently checked before a production implementation.

## Data grain / timing
**Required:** Synthetic dispute notices, collateral marks, haircut schedules, legal clocks, status and resolution labels
**Decision and publication clock:** Use values known to both parties at agreed margin timestamp; never use later corrected marks to excuse earlier action.
Required per source record: `observed_at_utc`, `published_at_utc`, `available_at_utc`, `effective_at_utc`, revision/version ID, legal use class, source proof and missingness marker. Never use postdecision publications or final revised data as historical knowledge.

## Explicit requirements
| Identifier | Requirement and trace |
|---|---|
| REQ-001 | Reconstruct permitted choice for: Resolve margin disagreements by independently identifying stale marks, eligibility mismatches and cut-off conventions. |
| REQ-002 | Baseline on matched opportunity set: FIFO triage by dispute amount and ticket keywords |
| REQ-003 | Research model: Deterministic valuation reconciliation then provenance-based root-cause ranking |
| REQ-004 | Falsify using: Seeded root-cause accuracy, false escalations, time-to-resolution, unresolved material exposure |
| NFR-001 | Deterministic seeds; auditable source, math and version manifest |
| NFR-002 | Fail closed for invalid rights, infeasible choices, conflicts and missing cost inputs |
| AC-001 | Synthetic fixture rejects future information and impossible states (REQ-001,NFR-001) |
| AC-002 | Exact/economically feasible baseline unit tests pass (REQ-002) |
| AC-003 | Candidate and baseline use identical contemporaneously feasible opportunities (REQ-003) |
| AC-004 | Holdout reports uncertainty and net economic downside, without winner-only selection (REQ-004) |
| AC-005 | Legal/publication/capacity controls forbid unauthorized outputs (NFR-002) |

## Scope, risks and stop/go
**Risk:** Conflicting vendor marks, jurisdiction-specific terms, privacy and LLM overconfidence.
**Stop research if:** LLM cannot improve verified resolver without hallucinated legal clauses or unacceptable false settlements.
**Non-goals:** live trade placement, confidential data release, automatic rule interpretation, unsupported empirical returns.
**Economic case (illustrative only):** $145k assumed total 24m development/data/maintenance cost; assumed launch in month 6; assumed annual gross outcome downside/base/upside $0k/$110k/$205k. Resulting 24m net ROI **-100.0% / 13.8% / 112.1% (downside/base/upside)**. These are invented transparent sensitivity inputs, not measured ROI, P&L, or investment advice.
**Evidence status:** no data access, code implementation, tests or paper novelty proof completed.
