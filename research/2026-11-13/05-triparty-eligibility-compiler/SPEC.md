# SPEC — Tri-Party Collateral Eligibility Clause-to-Constraint Compiler
**ID:** QMG-20261113-05 · **Status:** Draft; human approval required · **Category:** A · Securities finance · **Geography:** US triparty and secured funding

## Problem and decision
Collateral agreements express asset eligibility, issuer concentrations, haircuts and exceptions in natural language; manual transcription can generate allocation violations.
**Decision supported:** Compile approved eligibility schedules into testable constraints before collateral allocation, with human adjudication of ambiguous clauses.

## H1 versus H0
**H1:** A dual-path deterministic parser plus LLM reviewer reduces incorrect collateral acceptances versus manually transcribed spreadsheets.
**H0:** A cost-inclusive Rule tables hand-transcribed and checked by two human operators. matches or exceeds the candidate on strictly out-of-sample decisions. The intent is falsification, not confirmation.

## Mathematical problem and domain
```text
maximize Σ_(i,j) value_i*x_ij - substitution_cost_ij; x_ij<=eligible_ij; Σ_i exposure_ij<=limit_j
```
x_ij is amount of asset i allocated to collateral agreement j; eligible_ij is verified legal rule, not an LLM prediction.
**Capacity and eligibility:** Can serve as quality-gate software without trading access; execution requires approved legal rules and certified contracts.
Unspecified coefficients must be estimated only from training windows and no undocumented constraint may be relaxed.

## Source, clock and data contract
Synthetic collateral schedules; asset master; rating/issuer; eligibility categories; haircut tables; human-labeled clause examples. **Observation grain:** contract clause × effective version × collateral asset × valuation time. **Decision horizon:** rules valid at collateral decision; amendments apply from legal effective date, not document creation date.
At minimum require `observation_id`, `effective_at`, `published_at`, `available_at`, `ingested_at`, `source_uri`, `license_class`, `revision_id`, `unit`. `available_at <= decision_time` is mandatory for all market signals. New revisions create new records and must not silently overwrite historical decisions.

## Functional and nonfunctional requirements
| ID | Explicit requirement | Priority |
|---|---|---|
| REQ-001 | Model the permitted choice: Compile approved eligibility schedules into testable constraints before collateral allocation, with human adjudication of ambiguous clauses. | Must |
| REQ-002 | Reproduce feasible benchmark: Rule tables hand-transcribed and checked by two human operators. | Must |
| REQ-003 | Implement candidate Schema-constrained text extraction with symbolic eligibility evaluation and abstention. only after benchmark | Must |
| REQ-004 | Report false eligibility acceptance rate, false rejection rate, review labor, coverage, abstention, parse latency. and matched capacity/execution economics | Must |
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
USD $220k hypothetical 24-month engineering/data/maintenance cost; gross benefit sensitivity $95k–$365k over 24 months. Net ROI = (gross benefit − cost)/cost = **-57% to 66%**. NOT forecast or historical measurement. Economic lever: estimated 200–600 hours of manual eligibility review and avoided hypothetical exception remediations; unverified.. Source availability: Public clearing and securities-financing guidance gives domain patterns but not private triparty legal schedules.
Funding, transaction cost and execution constraints require separate real calibration.

## Primary risks and negative gates
- **RISK-001:** Natural-language ambiguity, contract precedence and jurisdiction-specific clauses make full automation unsafe.
- **RISK-002:** Data sparsity, nonstationarity, multiple testing and selection effects.
- **RISK-003:** Rights, settlement or investability restrictions may make an apparent opportunity infeasible.
- **Predeclared stop:** Reject if any critical false acceptance appears in stress fixtures or human review burden fails to improve.
- **Non-goals:** Trading, legal/compliance approvals, publishing real P&L, or deployment from this spec alone.
