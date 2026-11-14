# HANDOFF — EM External-Funding Fragility via Currency Mismatch and IIP
## Truthful current state
- **Research ID:** QMG-20261113-12 · **Status:** **DESIGN ONLY / NOT STARTED**.
- **Market:** Brazil, Mexico, South Africa, Indonesia, India and selected EM sovereigns.
- **Research owner:** unassigned; **independent quant/risk/legal reviewers:** unassigned.
- **Datasets downloaded:** none. **Tests executed:** none. **Actual P&L or ROI computed:** none. **Executable agent/runtime:** none.

## What the next research owner should do
1. Read [SPEC](./SPEC.md), [SOURCES](./SOURCES.md) and [EVALS](./EVALS.md).
2. Confirm source release and license for IMF IIP, BIS global liquidity quarterly FX credit, OECD macro where available, public reserve series and FX/sovereign returns..
3. Prepare synthetic point-in-time fixture using grain country × reporting quarter × first-public-availability time.
4. Implement the **Traditional sovereign credit rating tier, FX carry and three-month realized volatility.** cost-inclusive benchmark *before* Point-in-time standardized funding mismatch factor with recession/regime interactions..
5. Record negative results, uncertainty and source/quality caveats.

## Blockers and reasons
- Source limitation: BIS GLI and IMF IIP published quarterly with varying country coverage and revisions.
- Licensed/permissioned input gap: FX forward executable quotes, sovereign CDS, emerging-market rate/liquidity curves.
- Material science risk: Global liquidity metrics are quarterly; imputed weekly updates are model estimates, not observations.
- 24-month economics `-100% to 184%` reflect hypothetical sensitivity: hypothetical liquid $15m EM risk allocation where a small fraction of crash drawdown is avoided; no empirical hedge benefit.
- The named CLI/modules are proposed contracts only, not installed software.

## Novelty check against previous batch
Not cross-currency repo basis from prior work: studies cross-country external-balance vulnerability and sovereign/FX allocation.

## Reproducibility contract
Future work needs exact source/version timestamps, license/entitlement, decision clock, code hash, configuration, random seed, backtest period, rejection logs, solver tolerance, security/redaction check and independent signoff. None exists for this design-only batch.
