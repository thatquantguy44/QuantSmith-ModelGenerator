# PLAN — US Mortgage Origination Fall-Through and Rate-Lock Convexity
**QMG-20261127-19 | B — Domestic/global markets | US residential mortgage origination and rates | proposal only**
## Architecture
Source adapter → vintage/rights registry → mortgage-fallthrough-convexity state builder → baseline → candidate → matched economic replay → independent gate. Grain: application/lock × decision date; public HMDA annual cohort only. Data: loan outcomes, rates, application attributes, actual lock time, lock rate/expiry, hedge prices. Timing: public HMDA only after annual release; private locks timestamped before hedge; no demographic targeting.

## Model sequence
Baseline fixed pull-through by stage and loan type; candidate competing-risk duration model with rate gap; advanced joint hazard and convexity hedge with correlated fallout scenarios. Estimate on rolling training windows, tune only validation, freeze holdout and cost assumptions. Build a no-action comparator when capacity uncertain. Primary risk: HMDA lacks lock-level timestamps; public model cannot establish live hedge efficacy. No private data in repo.

## Proposed typed functions
load(as_of, source_ids)->versioned_rows; state(rows, cutoff)->mortgage-fallthrough-convexity decision states; baseline(states)->actions; candidate(states, config)->actions; evaluate(actions, outcomes)->hedge error, pull-through calibration, bias, cost and residual duration; validate() rejects withdrawals, lock extension, refi regime, future rate and applicant privacy. Map functions to REQ-001–004 and NFR-001/002; report missing inputs rather than fabricate. $100m average rate-locked pipeline × 10 bps hypothetical annual hedge improvement=$100k/year. Check actual costs/available liquidity before shadow. No implementation yet.
