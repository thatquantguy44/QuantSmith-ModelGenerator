# HANDOFF — Cash versus Noncash Loan-Collateral Economic Frontier
## Truthful current state
- **Research ID:** QMG-20261113-07 · **Status:** **DESIGN ONLY / NOT STARTED**.
- **Market:** US and international agent lending.
- **Research owner:** unassigned; **independent quant/risk/legal reviewers:** unassigned.
- **Datasets downloaded:** none. **Tests executed:** none. **Actual P&L or ROI computed:** none. **Executable agent/runtime:** none.

## What the next research owner should do
1. Read [SPEC](./SPEC.md), [SOURCES](./SOURCES.md) and [EVALS](./EVALS.md).
2. Confirm source release and license for Cash and noncash terms, rebate schedules, reinvestment constraints, asset eligibility, mark-to-market, haircuts and legal restrictions..
3. Prepare synthetic point-in-time fixture using grain loan offer × collateral type × owner mandate × quotation timestamp.
4. Implement the **Choose the highest headline loan spread among eligible offers.** cost-inclusive benchmark *before* Loan-specific all-in economic break-even and constraints solver..
5. Record negative results, uncertainty and source/quality caveats.

## Blockers and reasons
- Source limitation: Official repo market rates provide funding context; collateral-type price schedules are program-specific.
- Licensed/permissioned input gap: Commercial securities-lending fee/borrower collateral benchmark datasets.
- Material science risk: Comparing unavailable cash reinvestment yield to executable noncash economics creates phantom spread.
- 24-month economics `-62% to 114%` reflect hypothetical sensitivity: assume feasible switch of a small subset of a $400m average lending pool at 3–12 bps all-in uplift (unverified).
- The named CLI/modules are proposed contracts only, not installed software.

## Novelty check against previous batch
Unlike previous repo rate/haircut negotiation, evaluates securities-loan collateral alternatives at the *program owner* all-in economics level.

## Reproducibility contract
Future work needs exact source/version timestamps, license/entitlement, decision clock, code hash, configuration, random seed, backtest period, rejection logs, solver tolerance, security/redaction check and independent signoff. None exists for this design-only batch.
