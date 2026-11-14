# HANDOFF — Cash-Collateral Reinvestment Liquidity Run-Off Controller
## Truthful current state
- **Research ID:** QMG-20261113-02 · **Status:** **DESIGN ONLY / NOT STARTED**.
- **Market:** US securities lending programs.
- **Research owner:** unassigned; **independent quant/risk/legal reviewers:** unassigned.
- **Datasets downloaded:** none. **Tests executed:** none. **Actual P&L or ROI computed:** none. **Executable agent/runtime:** none.

## What the next research owner should do
1. Read [SPEC](./SPEC.md), [SOURCES](./SOURCES.md) and [EVALS](./EVALS.md).
2. Confirm source release and license for Loan termination flows; collateral principal; reinvestment settlement and maturity ladders; redemption windows; eligible funds; short-term yields; stress scenarios..
3. Prepare synthetic point-in-time fixture using grain cash collateral program × reinvestment maturity bucket × business day.
4. Implement the **Static liquidity buffer plus duration/weighted average life constraints.** cost-inclusive benchmark *before* Conditional run-off survival model combined with stochastic cash-flow gap optimizer..
5. Record negative results, uncertainty and source/quality caveats.

## Blockers and reasons
- Source limitation: Public SOFR and money-market rates can proxy the reinvestment curve, not private lending redemption behavior.
- Licensed/permissioned input gap: Short-term instrument prices and redemption proxy data with proper licensing.
- Material science risk: Return flows may cluster under crises; survivorship of reinvestment balances causes understated withdrawals.
- 24-month economics `-58% to 105%` reflect hypothetical sensitivity: hypothetical $600m collateral pool; avoid 1–5 days of emergency liquidity costs in a 24-month horizon; benefits depend on realized stress frequencies.
- The named CLI/modules are proposed contracts only, not installed software.

## Novelty check against previous batch
Unlike earlier intraday queue forecasts, focuses term maturity mismatch and loan-return tail risk at the reinvestment-portfolio level.

## Reproducibility contract
Future work needs exact source/version timestamps, license/entitlement, decision clock, code hash, configuration, random seed, backtest period, rejection logs, solver tolerance, security/redaction check and independent signoff. None exists for this design-only batch.
