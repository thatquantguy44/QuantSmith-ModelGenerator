# HANDOFF — Tri-Party Collateral Eligibility Clause-to-Constraint Compiler
## Truthful current state
- **Research ID:** QMG-20261113-05 · **Status:** **DESIGN ONLY / NOT STARTED**.
- **Market:** US triparty and secured funding.
- **Research owner:** unassigned; **independent quant/risk/legal reviewers:** unassigned.
- **Datasets downloaded:** none. **Tests executed:** none. **Actual P&L or ROI computed:** none. **Executable agent/runtime:** none.

## What the next research owner should do
1. Read [SPEC](./SPEC.md), [SOURCES](./SOURCES.md) and [EVALS](./EVALS.md).
2. Confirm source release and license for Synthetic collateral schedules; asset master; rating/issuer; eligibility categories; haircut tables; human-labeled clause examples..
3. Prepare synthetic point-in-time fixture using grain contract clause × effective version × collateral asset × valuation time.
4. Implement the **Rule tables hand-transcribed and checked by two human operators.** cost-inclusive benchmark *before* Schema-constrained text extraction with symbolic eligibility evaluation and abstention..
5. Record negative results, uncertainty and source/quality caveats.

## Blockers and reasons
- Source limitation: Public clearing and securities-financing guidance gives domain patterns but not private triparty legal schedules.
- Licensed/permissioned input gap: Licensed law/contract taxonomy and vendor eligibility schedules, if permitted.
- Material science risk: Natural-language ambiguity, contract precedence and jurisdiction-specific clauses make full automation unsafe.
- 24-month economics `-57% to 66%` reflect hypothetical sensitivity: estimated 200–600 hours of manual eligibility review and avoided hypothetical exception remediations; unverified.
- The named CLI/modules are proposed contracts only, not installed software.

## Novelty check against previous batch
Unlike prior collateral optimization and reuse stress models, the core research is legal rule extraction fidelity and solver-verified constraint generation.

## Reproducibility contract
Future work needs exact source/version timestamps, license/entitlement, decision clock, code hash, configuration, random seed, backtest period, rejection logs, solver tolerance, security/redaction check and independent signoff. None exists for this design-only batch.
