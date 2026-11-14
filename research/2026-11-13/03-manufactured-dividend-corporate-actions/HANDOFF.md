# HANDOFF — Manufactured-Dividend and Corporate-Action Loan Economics
## Truthful current state
- **Research ID:** QMG-20261113-03 · **Status:** **DESIGN ONLY / NOT STARTED**.
- **Market:** US and cross-listed global equities.
- **Research owner:** unassigned; **independent quant/risk/legal reviewers:** unassigned.
- **Datasets downloaded:** none. **Tests executed:** none. **Actual P&L or ROI computed:** none. **Executable agent/runtime:** none.

## What the next research owner should do
1. Read [SPEC](./SPEC.md), [SOURCES](./SOURCES.md) and [EVALS](./EVALS.md).
2. Confirm source release and license for Ex/record/pay dates; loan life; fee accrual; event elections; dividend amounts; owner tax flags and permitted return/recall rules..
3. Prepare synthetic point-in-time fixture using grain security × beneficial owner program × corporate-action event × decision timestamp.
4. Implement the **Renew if lending fee remains positive and return only upon explicit mandatory recall.** cost-inclusive benchmark *before* Rule-checked event economics and constrained loan life-cycle integer optimizer..
5. Record negative results, uncertainty and source/quality caveats.

## Blockers and reasons
- Source limitation: Public filings can anchor event timelines, but loan, tax and owner entitlement data are nonpublic.
- Licensed/permissioned input gap: Corporate-action master, dividend forecast and withholding/tax reference service with licensed rights.
- Material science risk: Tax withholding, treaty benefits and manufactured-dividend treatment cannot be assumed from issuer-country information alone.
- 24-month economics `-70% to 107%` reflect hypothetical sensitivity: illustrative prevention of a small number of high-value event-payment exceptions and legal-allowable tax drag over two years.
- The named CLI/modules are proposed contracts only, not installed software.

## Novelty check against previous batch
Different from earlier recall stopping-time proposals: treats corporate-action settlement and manufactured-payment accounting rather than predicting lender recall.

## Reproducibility contract
Future work needs exact source/version timestamps, license/entitlement, decision clock, code hash, configuration, random seed, backtest period, rejection logs, solver tolerance, security/redaction check and independent signoff. None exists for this design-only batch.
