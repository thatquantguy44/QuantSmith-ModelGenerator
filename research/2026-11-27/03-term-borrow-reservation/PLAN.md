# PLAN — Forward Borrow Capacity Reservation for Committed Term Loans
**QMG-20261127-03 | A — Securities finance | US and European equity stock loan | proposal only**
## Architecture
Source adapter → vintage/rights registry → term-borrow-reservation state builder → baseline → candidate → matched economic replay → independent gate. Grain: security × owner mandate × commitment vintage. Data: signed term commitments, available shares, draw schedules, spot fees, cancellations, replacement cost. Timing: at commitment acceptance or daily reserve review; only confirmed mandates and availability.

## Model sequence
Baseline fixed fraction of expected term draws, subject to same owner rights; candidate newsvendor quantile with censored draws and lead times; advanced multi-period distributionally robust reservation with scenario owner withdrawals. Estimate on rolling training windows, tune only validation, freeze holdout and cost assumptions. Build a no-action comparator when capacity uncertain. Primary risk: historical accepted demand is selected; inventory cannot be promised against unconfirmed availability. No private data in repo.

## Proposed typed functions
load(as_of, source_ids)->versioned_rows; state(rows, cutoff)->term-borrow-reservation decision states; baseline(states)->actions; candidate(states, config)->actions; evaluate(actions, outcomes)->shortage shares, realized reservation cost, service coverage, revenue; validate() rejects concurrent commitment consumes same shares; owner withdrawal; zero available shares. Map functions to REQ-001–004 and NFR-001/002; report missing inputs rather than fabricate. $250m eligible inventory × 8 bp/year avoided shortage/opportunity costs = $200k/year, after modeled variable frictions. Check actual costs/available liquidity before shadow. No implementation yet.
