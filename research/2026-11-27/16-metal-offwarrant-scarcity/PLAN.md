# PLAN — Exchange Metals Off-Warrant Inventory and Calendar-Spread Scarcity
**QMG-20261127-16 | B — Domestic/global markets | London Metal Exchange global base metals | proposal only**
## Architecture
Source adapter → vintage/rights registry → metal-offwarrant-scarcity state builder → baseline → candidate → matched economic replay → independent gate. Grain: metal × warehouse region × publication date. Data: off/on-warrant inventories, cancellations, warehouse movements, futures settlements, financing/storage costs. Timing: free data only after actual T+3 or current verified delay; paid T+1 separately; execute next quote.

## Model sequence
Baseline on-warrant stocks and curve momentum; candidate distributed-lag inventory/curve model; advanced latent location-transfer state model with inventory conservation. Estimate on rolling training windows, tune only validation, freeze holdout and cost assumptions. Build a no-action comparator when capacity uncertain. Primary risk: warrant cancellations can be relocation not end demand; data rights and warehouse incentives. No private data in repo.

## Proposed typed functions
load(as_of, source_ids)->versioned_rows; state(rows, cutoff)->metal-offwarrant-scarcity decision states; baseline(states)->actions; candidate(states, config)->actions; evaluate(actions, outcomes)->MAE, curve sign accuracy, net spread P&L, capacity; validate() rejects T+3 lag versus T+1 contamination; transfers double counted; contract roll. Map functions to REQ-001–004 and NFR-001/002; report missing inputs rather than fabricate. $60m risk sleeve × 15 bps annual net scenario=$90k/year; limit to liquid contract depth. Check actual costs/available liquidity before shadow. No implementation yet.
