# HANDOFF — Securities-Lending Fee Observability & Selection-Bias Corrector
## Truthful current state
- **Research ID:** QMG-20261113-08 · **Status:** **DESIGN ONLY / NOT STARTED**.
- **Market:** US/global securities lending benchmarks.
- **Research owner:** unassigned; **independent quant/risk/legal reviewers:** unassigned.
- **Datasets downloaded:** none. **Tests executed:** none. **Actual P&L or ROI computed:** none. **Executable agent/runtime:** none.

## What the next research owner should do
1. Read [SPEC](./SPEC.md), [SOURCES](./SOURCES.md) and [EVALS](./EVALS.md).
2. Confirm source release and license for Contributed executed fee samples; public security volume/short-interest proxies; locate response metadata; source coverage and revisions..
3. Prepare synthetic point-in-time fixture using grain security × lending day × vendor/contributor population.
4. Implement the **Daily equally weighted or outstanding-value-weighted observed market fees.** cost-inclusive benchmark *before* Doubly robust weighting with overlap and selection-sensitivity intervals..
5. Record negative results, uncertainty and source/quality caveats.

## Blockers and reasons
- Source limitation: Public security market data can inform context, but no complete free securities-loan execution tape is assumed.
- Licensed/permissioned input gap: Licensed securities-lending contribution feeds from multiple independent vendors.
- Material science risk: Missing-not-at-random selection cannot be identified from executed loans alone; confidence intervals can be falsely narrow.
- 24-month economics `-62% to 92%` reflect hypothetical sensitivity: scenario: avoid mispriced lending quotes on a small subset of specials; savings not inferable from the public sources alone.
- The named CLI/modules are proposed contracts only, not installed software.

## Novelty check against previous batch
Earlier auction allocation research assumed a demand model; this proposal quantifies vendor fee observability and confidence prior to any pricing choice.

## Reproducibility contract
Future work needs exact source/version timestamps, license/entitlement, decision clock, code hash, configuration, random seed, backtest period, rejection logs, solver tolerance, security/redaction check and independent signoff. None exists for this design-only batch.
