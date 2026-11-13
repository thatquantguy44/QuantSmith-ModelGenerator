# HANDOFF — Cross-Book Securities Finance Identity Reconciliation Graph
## Truthful current state
- **Research ID:** QMG-20261113-10 · **Status:** **DESIGN ONLY / NOT STARTED**.
- **Market:** US and cross-border securities-finance operations.
- **Research owner:** unassigned; **independent quant/risk/legal reviewers:** unassigned.
- **Datasets downloaded:** none. **Tests executed:** none. **Actual P&L or ROI computed:** none. **Executable agent/runtime:** none.

## What the next research owner should do
1. Read [SPEC](./SPEC.md), [SOURCES](./SOURCES.md) and [EVALS](./EVALS.md).
2. Confirm source release and license for Synthetic records containing lifecycle events, ISIN/CUSIP, product type, settlement date, amount, counterparty alias and amendment chain..
3. Prepare synthetic point-in-time fixture using grain source record × canonical candidate × event version × timestamp.
4. Implement the **Exact ID join plus manually triaged fuzzy-name matches.** cost-inclusive benchmark *before* Bipartite deterministic matching with hard identity constraints and provenance..
5. Record negative results, uncertainty and source/quality caveats.

## Blockers and reasons
- Source limitation: Official definitions guide field semantics, but real records remain private; publish only synthetic fixtures.
- Licensed/permissioned input gap: Reference security master/LEI mappings licensed from vendors, where legally permitted.
- Material science risk: LLM or probabilistic model can silently merge legally distinct entities or settlement legs.
- 24-month economics `-59% to 103%` reflect hypothetical sensitivity: scenario: 100–500 manual breaks annually at assumed fully loaded remediation costs; purely hypothetical.
- The named CLI/modules are proposed contracts only, not installed software.

## Novelty check against previous batch
Unlike prior settlement fail optimization, focuses pre-decision integrity and lineage of transaction identities as a standalone control.

## Reproducibility contract
Future work needs exact source/version timestamps, license/entitlement, decision clock, code hash, configuration, random seed, backtest period, rejection logs, solver tolerance, security/redaction check and independent signoff. None exists for this design-only batch.
