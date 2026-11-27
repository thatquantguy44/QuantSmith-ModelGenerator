# PLAN — Mexico Nearshoring Realization versus Industrial Equity Expectations
**QMG-20261127-12 | B — Domestic/global markets | Mexico, US–Mexico industrial corridor | proposal only**
## Architecture
Source adapter → vintage/rights registry → mexico-nearshoring-realization state builder → baseline → candidate → matched economic replay → independent gate. Grain: region × release month × issuer. Data: IMMEX staffing/hours, issuer geography, earnings, FX, exports, corporate announcements. Timing: first INEGI monthly release and financial report timestamps, region weights frozen before prediction.

## Model sequence
Baseline FX/export growth plus issuer lagged earnings; candidate hierarchical exposure-weighted panel forecast; advanced dynamic factor with announcement-versus-realization measurement error. Estimate on rolling training windows, tune only validation, freeze holdout and cost assumptions. Build a no-action comparator when capacity uncertain. Primary risk: IMMEX program composition shifts; firms disclose incomplete plant geography. No private data in repo.

## Proposed typed functions
load(as_of, source_ids)->versioned_rows; state(rows, cutoff)->mexico-nearshoring-realization decision states; baseline(states)->actions; candidate(states, config)->actions; evaluate(actions, outcomes)->MAE, revision sensitivity, sector-neutral forecast IC; validate() rejects future revisions, missing plant map, peso shock, announcement placebo. Map functions to REQ-001–004 and NFR-001/002; report missing inputs rather than fabricate. $80m research sleeve × 10 bps annual decision improvement=$80k/year after turnover, capacity unverified. Check actual costs/available liquidity before shadow. No implementation yet.
