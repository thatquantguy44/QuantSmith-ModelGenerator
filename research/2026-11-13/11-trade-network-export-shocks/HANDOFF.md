# HANDOFF — Trade-Network Export-Shock Transmission to Equity Sectors
## Truthful current state
- **Research ID:** QMG-20261113-11 · **Status:** **DESIGN ONLY / NOT STARTED**.
- **Market:** US, Mexico, Germany, Japan, Korea, China and ASEAN markets.
- **Research owner:** unassigned; **independent quant/risk/legal reviewers:** unassigned.
- **Datasets downloaded:** none. **Tests executed:** none. **Actual P&L or ROI computed:** none. **Executable agent/runtime:** none.

## What the next research owner should do
1. Read [SPEC](./SPEC.md), [SOURCES](./SOURCES.md) and [EVALS](./EVALS.md).
2. Confirm source release and license for UN Comtrade reported and partner-reported trade by HS code/month; sector country revenue mix; FX; sector returns and macro controls..
3. Prepare synthetic point-in-time fixture using grain reporter × partner × HS code × reference month × publication/availability timestamp.
4. Implement the **Equal-weight country sector allocation with FX and local industrial production controls.** cost-inclusive benchmark *before* Sparse directed trade graph factor with event-lag-aware regressions..
5. Record negative results, uncertainty and source/quality caveats.

## Blockers and reasons
- Source limitation: UN Comtrade public preview has limited records; full historical coverage may require free keyed or premium bulk access.
- Licensed/permissioned input gap: Licensed country-sector total returns, revenue segment exposures and comprehensive Comtrade extracts.
- Material science risk: Revisions, late reporters, trade re-exports and mapping HS codes to listed firms can create survivorship and spurious exposure.
- 24-month economics `-100% to 247%` reflect hypothetical sensitivity: hypothetical $10m liquid sector sleeve and 0–260 bps gross annualized alpha capture over 2 years; zero base benefit is plausible.
- The named CLI/modules are proposed contracts only, not installed software.

## Novelty check against previous batch
Unlike prior financing-market inventory or derivatives signals, this is a global real-economy propagation graph linking trade records to listed sector risk.

## Reproducibility contract
Future work needs exact source/version timestamps, license/entitlement, decision clock, code hash, configuration, random seed, backtest period, rejection logs, solver tolerance, security/redaction check and independent signoff. None exists for this design-only batch.
