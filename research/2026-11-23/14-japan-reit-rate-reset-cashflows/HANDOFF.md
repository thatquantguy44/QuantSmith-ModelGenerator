# HANDOFF — Japanese Real-Estate Equity Cash-Flow Sensitivity to BOJ Rate Normalization
**Status:** research design delivered, **all empirical and executable work BLOCKED/not started**. Owner, legal reviewer and dataset approver: not assigned.

## Transfer to implementing researcher
**Economic decision:** Distinguish J-REIT rate-reset liability timing and property yield spreads rather than duration-only price sensitivity.
**Falsifiable claim:** Public debt-maturity reset exposure explains post-policy J-REIT return dispersion beyond NAV discount and generic duration beta.
**First deliverable:** synthetic/point-in-time fixture and reproducible `Market REIT index duration and price-to-NAV score`.
**Then:** Disclosure-derived maturity-wall factor with event-based hedged return regressions.
**Stop:** No incremental post-rate-shift forecast after issuer fixed-effects and NAV-duration controls..

## Required unresolved inputs
- Licence and historical access for TSE J-REIT historical prices and Japanese property rent indices.
- Exact public timestamp/version contract: Use release/filing acceptance before BOJ event and timestamp debt disclosure versions.
- Authorized reference data (never to GitHub): Approved real estate securities trade cost estimates.
- Correct edge treatment: Japanese disclosure translation/lease renewal timing and selective REIT survivorship..
- Realizable economics: J-REIT constituent liquidity, FX hedge and foreign-investor restrictions limit realized capacity..

## Reproducibility
Pin source URL/version/time, commit, configuration hash, calendar, random seed, solver tolerance, excluded instrument list and holdout. Preserve failed/negative tests, claims and uncertainty.

## Financial scope
$150k assumed total 24m development/data/maintenance cost; assumed launch in month 7; assumed annual gross outcome downside/base/upside $0k/$85k/$235k. Resulting 24m net ROI **-100.0% / -19.7% / 121.9% (downside/base/upside)**. These are invented transparent sensitivity inputs, not measured ROI, P&L, or investment advice.
Scores and sensitivities are design judgments, not alpha or observed savings. Reviewer must explicitly accept evidence before moving to shadow mode.
