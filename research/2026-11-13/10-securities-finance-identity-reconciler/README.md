# Cross-Book Securities Finance Identity Reconciliation Graph
**A · Securities finance** · **Priority 86/100** · **Difficulty Medium** · **Feasibility: High as deterministic software** · **Publication interest 3/5 (conceptual, not a paper).**

## Why this exists
Trade/loan, security and collateral IDs can diverge across booking, servicing and settlement systems, producing false liquidity constraints and duplicated risk.

**Market / geography:** US and cross-border securities-finance operations. **Asset classes:** repo, stock loan, collateral, settlement reference data.

## Falsifiable hypothesis and investment/operational decision
A provenance-aware deterministic graph matcher reduces unresolved break hours and false exposure duplications compared with fuzzy string matching.

**Decision:** Resolve and quarantine inconsistent identities before financing position, collateral and exposure optimization..

## Research model
```text
min_M Σ_(i,j) c_ij*M_ij + λ*unmatched(M); M_ij∈{0,1}, one-to-one constraints and incompatible identifier rules
```
M_ij selects a candidate match between external and canonical records; c_ij is audited mismatch cost with hard ID prohibitions.

## Data and decision clock
Synthetic records containing lifecycle events, ISIN/CUSIP, product type, settlement date, amount, counterparty alias and amendment chain. **Observation grain:** source record × canonical candidate × event version × timestamp. **Decision horizon:** real-time/overnight reconciliation; no future correction can be applied retroactively to a prior risk snapshot.

## Baseline versus candidate
- **Baseline:** Exact ID join plus manually triaged fuzzy-name matches.
- **Proposed model:** Bipartite deterministic matching with hard identity constraints and provenance.
- **Advanced option:** Human-review active-learning on uncertain clusters with error budget and privacy-preserving synthetic tests.
- **Primary metrics:** false merge rate, unmatched %, time to resolve, duplicate exposure USD, manual review hours.
- **Falsification:** Reject if critical false merges exceed zero in labeled holdouts or operations time does not decline.
- **Primary economic or methodological caveat:** LLM or probabilistic model can silently merge legally distinct entities or settlement legs.

## 24-month ROI sensitivity (unverified assumptions only)
USD $145k hypothetical 24-month engineering/data/maintenance cost; gross benefit sensitivity $60k–$295k over 24 months. Net ROI = (gross benefit − cost)/cost = **-59% to 103%**. NOT forecast or historical measurement. Economic lever: scenario: 100–500 manual breaks annually at assumed fully loaded remediation costs; purely hypothetical.

## Execution, capacity and feasibility
No market capacity required; scalability measured in records/day and audit/log cost, not claimed P&L.

## Research documents
[SPEC](./SPEC.md) · [PLAN](./PLAN.md) · [TASKS](./TASKS.md) · [ROADMAP](./ROADMAP.md) · [HANDOFF](./HANDOFF.md) · [SOURCES](./SOURCES.md) · [EVALS](./EVALS.md)

## Reusable agent and engineering contracts
[AGENT](./AGENT.md) · [SKILL](./SKILL.md) · [PROMPT](./PROMPT.md) · [TOOLING](./TOOLING.md) · [WORKFLOW](./WORKFLOW.md) · [RUNTIME](./RUNTIME.md)

**Status: NOT STARTED.** These are specific scientific and engineering proposals, not executable deployments, experimental findings or empirically verified strategies.
