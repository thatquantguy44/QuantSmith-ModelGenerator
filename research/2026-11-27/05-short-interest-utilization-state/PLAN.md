# PLAN — Short Interest versus Securities Loan Utilization State Decomposition
**QMG-20261127-05 | A — Securities finance | US exchange-listed equities | proposal only**
## Architecture
Source adapter → vintage/rights registry → short-interest-utilization-state state builder → baseline → candidate → matched economic replay → independent gate. Grain: issuer × share class × trading day / short-interest publication. Data: reported SI, lender availability/utilization, corporate actions, lendable supply and fees. Timing: ingest FINRA publication after 4:40 p.m. ET or later actual receipt; trade next eligible session.

## Model sequence
Baseline autoregression on utilization and market returns; candidate constrained state-space model with delayed SI observation; advanced hierarchical particle filter with split-adjusted latent demand/supply regime. Estimate on rolling training windows, tune only validation, freeze holdout and cost assumptions. Build a no-action comparator when capacity uncertain. Primary risk: short interest is not total loans, coverage differs by vendor and share class. No private data in repo.

## Proposed typed functions
load(as_of, source_ids)->versioned_rows; state(rows, cutoff)->short-interest-utilization-state decision states; baseline(states)->actions; candidate(states, config)->actions; evaluate(actions, outcomes)->MAE, calibration, supply/demand label precision on verified events; validate() rejects synthetic split, delayed publication, denominator near zero, shuffled release labels. Map functions to REQ-001–004 and NFR-001/002; report missing inputs rather than fabricate. $200m addressable repricing inventory × 5 bps net annual improvement = $100k/year; conditional on actual policy benefit. Check actual costs/available liquidity before shadow. No implementation yet.
