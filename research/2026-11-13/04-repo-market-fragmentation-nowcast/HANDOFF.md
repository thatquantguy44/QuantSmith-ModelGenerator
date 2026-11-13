# HANDOFF — Cleared Versus Tri-Party Repo Fragmentation Nowcast
## Truthful current state
- **Research ID:** QMG-20261113-04 · **Status:** **DESIGN ONLY / NOT STARTED**.
- **Market:** United States short-term funding markets.
- **Research owner:** unassigned; **independent quant/risk/legal reviewers:** unassigned.
- **Datasets downloaded:** none. **Tests executed:** none. **Actual P&L or ROI computed:** none. **Executable agent/runtime:** none.

## What the next research owner should do
1. Read [SPEC](./SPEC.md), [SOURCES](./SOURCES.md) and [EVALS](./EVALS.md).
2. Confirm source release and license for OFR cleared and tri-party rate-volume series; collateral categories; SOFR; weekly dealer aggregate financing; release metadata..
3. Prepare synthetic point-in-time fixture using grain venue × collateral class × tenor × underlying observation date, plus public publication timestamp.
4. Implement the **SOFR level change and aggregate funding volume z-score.** cost-inclusive benchmark *before* State-space latent fragmentation index with lag-aware missingness..
5. Record negative results, uncertainty and source/quality caveats.

## Blockers and reasons
- Source limitation: OFR reports secured funding data with documented one- and two-day publication lags and confidentiality blanks.
- Licensed/permissioned input gap: Intraday OTC repo RFQ execution feeds to investigate tradability; not required for a public risk research prototype.
- Material science risk: Revised/missing suppressed OFR cells and cross-venue holiday timing can create lookahead and artificial divergences.
- 24-month economics `-68% to 68%` reflect hypothetical sensitivity: scenario: avoid one or two large risk-buffer errors or reduce manual funding surveillance effort; no P&L is proven.
- The named CLI/modules are proposed contracts only, not installed software.

## Novelty check against previous batch
Different from prior repo curve specialness and balance-sheet calendar ideas; targets venue fragmentation surveillance using public as-released aggregates.

## Reproducibility contract
Future work needs exact source/version timestamps, license/entitlement, decision clock, code hash, configuration, random seed, backtest period, rejection logs, solver tolerance, security/redaction check and independent signoff. None exists for this design-only batch.
