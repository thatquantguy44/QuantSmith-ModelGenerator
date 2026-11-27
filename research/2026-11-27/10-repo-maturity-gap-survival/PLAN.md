# PLAN — Repo Maturity Mismatch Early-Warning via Survival Cash Ladders
**QMG-20261127-10 | A — Securities finance | US and European matched-book secured funding | proposal only**
## Architecture
Source adapter → vintage/rights registry → repo-maturity-gap-survival state builder → baseline → candidate → matched economic replay → independent gate. Grain: repo trade × maturity bucket × daily snapshot. Data: maturity dates, historical renewals/nonrenewals, counterparty segment, rates, confirmed inflows and cutoff. Timing: decision before maturity; only renewals confirmed by snapshot; outcomes as labels.

## Model sequence
Baseline contractual maturity ladder with fixed stress rollover percentage; candidate competing-risk survival and calibrated gap scenarios; advanced hierarchical regime-dependent survival with correlated nonrenewal. Estimate on rolling training windows, tune only validation, freeze holdout and cost assumptions. Build a no-action comparator when capacity uncertain. Primary risk: censoring of renewals and structural shifts; predicted rollover not assured liquidity. No private data in repo.

## Proposed typed functions
load(as_of, source_ids)->versioned_rows; state(rows, cutoff)->repo-maturity-gap-survival decision states; baseline(states)->actions; candidate(states, config)->actions; evaluate(actions, outcomes)->Brier score, cash-gap quantile coverage, warning lead time, reserve cost; validate() rejects no renewals in stress, maturity concentration, missing confirmations. Map functions to REQ-001–004 and NFR-001/002; report missing inputs rather than fabricate. $4m avoided excess average reserve × 3% net carrying cost=$120k/year; no relaxation of required liquidity. Check actual costs/available liquidity before shadow. No implementation yet.
