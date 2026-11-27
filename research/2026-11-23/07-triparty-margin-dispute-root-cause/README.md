# Tri-Party Repo Margin Dispute Root-Cause and Evidence Classifier
**ID:** B17-07 · **Group:** Securities finance · **Geography:** US and European tri-party collateral · **Priority:** 89/100 · **Status:** not implemented

## Economic decision and hypothesis
Operational margin disputes are often triaged from unstructured tickets without reconstructing mark, haircut and event timing.

**Decision:** Resolve margin disagreements by independently identifying stale marks, eligibility mismatches and cut-off conventions.

**H1:** A deterministic calculation engine plus provenance graph resolves more disputes correctly than keyword-based ticket routing.

## Formulation
```text
DisputeAmount_j=Σ_i (Mark_{i,t}*(1-h_i)*Qty_i)_bank - Σ_i (Mark_{i,t}*(1-h_i)*Qty_i)_agent
```
**Variables:** h_i haircut and Mark_i mark at contractual timestamp; compare sides only when valuation basis matches.

**Data:** Synthetic dispute notices, collateral marks, haircut schedules, legal clocks, status and resolution labels

**Clock:** Use values known to both parties at agreed margin timestamp; never use later corrected marks to excuse earlier action.

**Baseline:** FIFO triage by dispute amount and ticket keywords; **candidate:** Deterministic valuation reconciliation then provenance-based root-cause ranking; **advanced:** Constrained language-model document extraction with deterministic verifier and abstain-on-conflict.

**Evaluation:** Seeded root-cause accuracy, false escalations, time-to-resolution, unresolved material exposure. **Failure:** LLM cannot improve verified resolver without hallucinated legal clauses or unacceptable false settlements.

**Capacity:** Operational capacity limited by manual reviewer; never auto-settle margin on agent output.

**Illustrative sensitivity:** $145k assumed total 24m development/data/maintenance cost; assumed launch in month 6; assumed annual gross outcome downside/base/upside $0k/$110k/$205k. Resulting 24m net ROI **-100.0% / 13.8% / 112.1% (downside/base/upside)**. These are invented transparent sensitivity inputs, not measured ROI, P&L, or investment advice.

## Documents
[SPEC](./SPEC.md) · [PLAN](./PLAN.md) · [TASKS](./TASKS.md) · [ROADMAP](./ROADMAP.md) · [HANDOFF](./HANDOFF.md) · [SOURCES](./SOURCES.md) · [AGENT](./AGENT.md) · [SKILL](./SKILL.md) · [PROMPT](./PROMPT.md) · [TOOLING](./TOOLING.md) · [WORKFLOW](./WORKFLOW.md) · [RUNTIME](./RUNTIME.md) · [EVALS](./EVALS.md)

**No empirical model execution, licensing approval, dataset download, trading result or implemented AI runtime is claimed.**
