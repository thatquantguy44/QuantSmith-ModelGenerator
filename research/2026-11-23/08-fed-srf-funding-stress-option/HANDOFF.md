# HANDOFF — Fed Standing Repo Facility as a Funding-Stress Option Exercise Signal
**Status:** research design delivered, **all empirical and executable work BLOCKED/not started**. Owner, legal reviewer and dataset approver: not assigned.

## Transfer to implementing researcher
**Economic decision:** Monitor time-lagged facility usage and infer when broad repo funding stress warrants buffer review.
**Falsifiable claim:** Publication-aligned SRF utilization and awarded-rate dispersion improve next-session funding stress classification beyond SOFR-GC spread alone.
**First deliverable:** synthetic/point-in-time fixture and reproducible `SOFR-GC spread threshold with no SRF information`.
**Then:** Event-conditioned calibrated logistic hazard with lag-safe publication ledger.
**Stop:** No holdout information gain after timing correction, or false positives overwhelm funding buffer costs..

## Required unresolved inputs
- Licence and historical access for Intraday secured-funding quotations and market depth.
- Exact public timestamp/version contract: Use posted operation result time and repo series 1-2-day publication lags; do not use same-day hidden participant-level bids.
- Authorized reference data (never to GitHub): Permissioned liquidity buffers/cash funding obligations for downstream assessment.
- Correct edge treatment: SRF operational parameter changes, known policy regime shifts, lack of entity-level same-day data..
- Realizable economics: Research output is risk-monitoring, not direct trading opportunity; facility eligibility and costs differ by participant..

## Reproducibility
Pin source URL/version/time, commit, configuration hash, calendar, random seed, solver tolerance, excluded instrument list and holdout. Preserve failed/negative tests, claims and uncertainty.

## Financial scope
$115k assumed total 24m development/data/maintenance cost; assumed launch in month 5; assumed annual gross outcome downside/base/upside $0k/$70k/$170k. Resulting 24m net ROI **-100.0% / -3.6% / 134.1% (downside/base/upside)**. These are invented transparent sensitivity inputs, not measured ROI, P&L, or investment advice.
Scores and sensitivities are design judgments, not alpha or observed savings. Reviewer must explicitly accept evidence before moving to shadow mode.
