# HANDOFF — Repo Coupon and Principal Event Cash-Flow Netting Scheduler
**Status:** research design delivered, **all empirical and executable work BLOCKED/not started**. Owner, legal reviewer and dataset approver: not assigned.

## Transfer to implementing researcher
**Economic decision:** Minimize same-day cash deficits caused by collateral coupon/principal flows and contractual manufactured payments.
**Falsifiable claim:** Event-aware legally permissible netting reduces liquidity buffer and operational exceptions versus cash-flow-independent settlement.
**First deliverable:** synthetic/point-in-time fixture and reproducible `Gross independent payment processing with static buffer`.
**Then:** Mixed-integer liquidity scheduling with eligibility/netting-set constraints.
**Stop:** No capacity-adjusted cost reduction versus pre-netted conventional operations or violations of payment rights..

## Required unresolved inputs
- Licence and historical access for Securities master coupon and settlement event feeds.
- Exact public timestamp/version contract: Coupon schedule published at issuance; adjustments and confirmed obligations only after contract notice timestamp.
- Authorized reference data (never to GitHub): Authorized repo contracts and cash-settlement messages.
- Correct edge treatment: Wrong beneficial-ownership treatment, netting rights and special cash settlement terms..
- Realizable economics: Savings limited to payments legally eligible for netting; reconciliation costs, daylight overdraft fees and solver latency included..

## Reproducibility
Pin source URL/version/time, commit, configuration hash, calendar, random seed, solver tolerance, excluded instrument list and holdout. Preserve failed/negative tests, claims and uncertainty.

## Financial scope
$120k assumed total 24m development/data/maintenance cost; assumed launch in month 5; assumed annual gross outcome downside/base/upside $0k/$95k/$190k. Resulting 24m net ROI **-100.0% / 25.3% / 150.7% (downside/base/upside)**. These are invented transparent sensitivity inputs, not measured ROI, P&L, or investment advice.
Scores and sensitivities are design judgments, not alpha or observed savings. Reviewer must explicitly accept evidence before moving to shadow mode.
