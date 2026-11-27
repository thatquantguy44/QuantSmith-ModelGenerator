# PLAN — Collateral Substitution with Discrete Lot Opportunity Costs
**QMG-20261127-01 | A — Securities finance | US Treasury and European sovereign repo | proposal only**
## Architecture
Source adapter → vintage/rights registry → collateral-lot-substitution state builder → baseline → candidate → matched economic replay → independent gate. Grain: lot × obligation × snapshot. Data: lot size, live eligibility, haircut, encumbrance, transfer fees, cutoffs, available inventory and replacement opportunity cost. Timing: pre-substitution snapshot; confirm replacement settlement before release; no end-day inventory.

## Model sequence
Baseline cheapest eligible collateral first with same lot and transfer constraints; candidate integer min-cost assignment with opportunity-cost duals; advanced rolling stochastic mixed-integer control with replacement failure recourse. Estimate on rolling training windows, tune only validation, freeze holdout and cost assumptions. Build a no-action comparator when capacity uncertain. Primary risk: solver can suggest illegal or unsettled substitution if pending collateral is counted. No private data in repo.

## Proposed typed functions
load(as_of, source_ids)->versioned_rows; state(rows, cutoff)->collateral-lot-substitution decision states; baseline(states)->actions; candidate(states, config)->actions; evaluate(actions, outcomes)->net USD carry/transfer cost, excess collateral, breach count, solve time; validate() rejects one scarce lot assigned twice; replacement not final; haircut shock; infeasible obligation. Map functions to REQ-001–004 and NFR-001/002; report missing inputs rather than fabricate. Assume $1bn average eligible inventory and 2 bps annual gross opportunity improvement, less $40k transfer overhead; $160k/year net before project costs. Check actual costs/available liquidity before shadow. No implementation yet.
