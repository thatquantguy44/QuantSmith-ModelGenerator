# HANDOFF — Borrow Scarcity Causal Effect on Equity Market-Maker Quoted Depth
**Status:** research design delivered, **all empirical and executable work BLOCKED/not started**. Owner, legal reviewer and dataset approver: not assigned.

## Transfer to implementing researcher
**Economic decision:** Adjust financing risk capital for equity liquidity provision when short-sale borrow becomes scarce.
**Falsifiable claim:** Exogenous changes to borrow supply lower subsequent displayed depth/increase effective spreads more than matched control stocks.
**First deliverable:** synthetic/point-in-time fixture and reproducible `Spread/depth forecasting using only realized volatility and market cap`.
**Then:** Matched differences-in-differences/event-time instrumental analysis.
**Stop:** No pre-registered effect with valid pretrends/instruments or effect only on illiquid untradeable names..

## Required unresolved inputs
- Licence and historical access for LOBSTER/order book or exchange TAQ and securities-lending locates.
- Exact public timestamp/version contract: Quote-decision timing after actual supply notice; event timestamps distinguish pre-event leak, regular session and close.
- Authorized reference data (never to GitHub): Authorized lending supply events and market-making decisions.
- Correct edge treatment: Selection on distressed shorts, simultaneous volatility and hard-to-borrow endogenous events..
- Realizable economics: Not an unconditional trading signal; capacity depends on quote depth and borrow clearance, include adverse selection..

## Reproducibility
Pin source URL/version/time, commit, configuration hash, calendar, random seed, solver tolerance, excluded instrument list and holdout. Preserve failed/negative tests, claims and uncertainty.

## Financial scope
$220k assumed total 24m development/data/maintenance cost; assumed launch in month 9; assumed annual gross outcome downside/base/upside $0k/$120k/$310k. Resulting 24m net ROI **-100.0% / -31.8% / 76.1% (downside/base/upside)**. These are invented transparent sensitivity inputs, not measured ROI, P&L, or investment advice.
Scores and sensitivities are design judgments, not alpha or observed savings. Reviewer must explicitly accept evidence before moving to shadow mode.
