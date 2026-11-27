# PLAN — Partial Securities Delivery Allocation under Minimum Lot Rules
**QMG-20261127-06 | A — Securities finance | US and European securities settlement | proposal only**
## Architecture
Source adapter → vintage/rights registry → partial-delivery-lot-allocation state builder → baseline → candidate → matched economic replay → independent gate. Grain: security × settlement instruction × cutoff snapshot. Data: remaining obligations, settled inventory, minimum lot, partial permission, costs, deadlines and acknowledgments. Timing: before each cutoff with confirmed deliverable stock; pending receipts excluded.

## Model sequence
Baseline earliest-deadline-first full delivery; candidate integer allocation with minimum partial sizes; advanced two-stage stochastic delivery with confirmed receipts and recourse. Estimate on rolling training windows, tune only validation, freeze holdout and cost assumptions. Build a no-action comparator when capacity uncertain. Primary risk: partial processing overhead and legal restrictions differ by venue. No private data in repo.

## Proposed typed functions
load(as_of, source_ids)->versioned_rows; state(rows, cutoff)->partial-delivery-lot-allocation decision states; baseline(states)->actions; candidate(states, config)->actions; evaluate(actions, outcomes)->weighted undelivered shares, net fail fees, message count, missed cutoffs; validate() rejects lot above remainder; negative inventory; all-or-nothing flag; delayed acknowledgement. Map functions to REQ-001–004 and NFR-001/002; report missing inputs rather than fabricate. 40k eligible instructions/year × $4 avoidable weighted cost = $160k/year, after message costs. Check actual costs/available liquidity before shadow. No implementation yet.
