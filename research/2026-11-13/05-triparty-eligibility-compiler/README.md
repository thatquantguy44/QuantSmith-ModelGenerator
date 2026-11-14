# Tri-Party Collateral Eligibility Clause-to-Constraint Compiler
**A · Securities finance** · **Priority 91/100** · **Difficulty High** · **Feasibility: Medium pending contract access** · **Publication interest 4/5 (conceptual, not a paper).**

## Why this exists
Collateral agreements express asset eligibility, issuer concentrations, haircuts and exceptions in natural language; manual transcription can generate allocation violations.

**Market / geography:** US triparty and secured funding. **Asset classes:** repo collateral eligibility and documentation.

## Falsifiable hypothesis and investment/operational decision
A dual-path deterministic parser plus LLM reviewer reduces incorrect collateral acceptances versus manually transcribed spreadsheets.

**Decision:** Compile approved eligibility schedules into testable constraints before collateral allocation, with human adjudication of ambiguous clauses..

## Research model
```text
maximize Σ_(i,j) value_i*x_ij - substitution_cost_ij; x_ij<=eligible_ij; Σ_i exposure_ij<=limit_j
```
x_ij is amount of asset i allocated to collateral agreement j; eligible_ij is verified legal rule, not an LLM prediction.

## Data and decision clock
Synthetic collateral schedules; asset master; rating/issuer; eligibility categories; haircut tables; human-labeled clause examples. **Observation grain:** contract clause × effective version × collateral asset × valuation time. **Decision horizon:** rules valid at collateral decision; amendments apply from legal effective date, not document creation date.

## Baseline versus candidate
- **Baseline:** Rule tables hand-transcribed and checked by two human operators.
- **Proposed model:** Schema-constrained text extraction with symbolic eligibility evaluation and abstention.
- **Advanced option:** Contradiction-aware graph of rule amendments with formal test generation and reviewer feedback.
- **Primary metrics:** false eligibility acceptance rate, false rejection rate, review labor, coverage, abstention, parse latency.
- **Falsification:** Reject if any critical false acceptance appears in stress fixtures or human review burden fails to improve.
- **Primary economic or methodological caveat:** Natural-language ambiguity, contract precedence and jurisdiction-specific clauses make full automation unsafe.

## 24-month ROI sensitivity (unverified assumptions only)
USD $220k hypothetical 24-month engineering/data/maintenance cost; gross benefit sensitivity $95k–$365k over 24 months. Net ROI = (gross benefit − cost)/cost = **-57% to 66%**. NOT forecast or historical measurement. Economic lever: estimated 200–600 hours of manual eligibility review and avoided hypothetical exception remediations; unverified.

## Execution, capacity and feasibility
Can serve as quality-gate software without trading access; execution requires approved legal rules and certified contracts.

## Research documents
[SPEC](./SPEC.md) · [PLAN](./PLAN.md) · [TASKS](./TASKS.md) · [ROADMAP](./ROADMAP.md) · [HANDOFF](./HANDOFF.md) · [SOURCES](./SOURCES.md) · [EVALS](./EVALS.md)

## Reusable agent and engineering contracts
[AGENT](./AGENT.md) · [SKILL](./SKILL.md) · [PROMPT](./PROMPT.md) · [TOOLING](./TOOLING.md) · [WORKFLOW](./WORKFLOW.md) · [RUNTIME](./RUNTIME.md)

**Status: NOT STARTED.** These are specific scientific and engineering proposals, not executable deployments, experimental findings or empirically verified strategies.
