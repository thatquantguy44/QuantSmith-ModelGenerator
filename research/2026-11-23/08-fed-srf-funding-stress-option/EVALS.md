# EVALS — Fed Standing Repo Facility as a Funding-Stress Option Exercise Signal
**No empirical test run. Evaluation design, not evidence.**

## H1/H0 and economics
H1: Publication-aligned SRF utilization and awarded-rate dispersion improve next-session funding stress classification beyond SOFR-GC spread alone.
H0: the feasible `SOFR-GC spread threshold with no SRF information` benchmark is not improved net of risk/cost.
Candidate: `Event-conditioned calibrated logistic hazard with lag-safe publication ledger`. Advanced: Structural real-option exercise mapping latent facility usage and dealer cash constraints
Metrics: Brier score, AUPRC, stress false alarm, lead-time, calibrated probability.

## Mandatory synthetic invariants
- `available_at_utc <= decision_time`, calendar/session alignment and source-version hash.
- Feasible decision constraints match: P(Stress_{t+1}=1|F_t)=logit^{-1}(β0+β1*SRFAward_t+β2*RateDisp_t+β3*SOFRSpread_t).
- Units and payable/receivable cash direction from: Stress is pre-defined funding event; F_t contains only SRF summary published by decision time.
- True negative controls: SRF operational parameter changes, known policy regime shifts, lack of entity-level same-day data.
- Equal event/asset universe, quoted bid/ask, capacity and no-action alternatives.

## Empirical design if licensed data eventually approved
Time-blocked train/validation/holdout, embargo overlaps and original-vintage release lags. Conduct matched policy replay, bootstrap by independent event block, monitor false discoveries across multiple choices, expose failed dates and liquidity drawdowns.
**Stop:** No holdout information gain after timing correction, or false positives overwhelm funding buffer costs..

## Cost and publication
Research output is risk-monitoring, not direct trading opportunity; facility eligibility and costs differ by participant.
$115k assumed total 24m development/data/maintenance cost; assumed launch in month 5; assumed annual gross outcome downside/base/upside $0k/$70k/$170k. Resulting 24m net ROI **-100.0% / -3.6% / 134.1% (downside/base/upside)**. These are invented transparent sensitivity inputs, not measured ROI, P&L, or investment advice.
Public papers and official datasets are context only, not replication. Any material positive result requires independently reproduced code + signed human review; no automatic trading.

## Acceptance gating
AC-001..AC-005 from SPEC each requires a runnable test record and model/data rights signoff. If source is incomplete, report a negative or blocked result, not a proxy alpha claim.
