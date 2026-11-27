# PLAN — Accrual Cash-Conversion Reversal with XBRL Restatement Lineage
**QMG-20261127-15 | B — Domestic/global markets | US and foreign SEC reporting equities | proposal only**
## Architecture
Source adapter → vintage/rights registry → xbrl-cash-conversion-reversal state builder → baseline → candidate → matched economic replay → independent gate. Grain: issuer CIK × fiscal quarter × filing accession × tag. Data: cash flow, net income, assets, receivables, inventory, restatements, taxonomy mappings and delisting records. Timing: first filing acceptance/dissemination, with later amended accession separate; decisions next session.

## Model sequence
Baseline total accrual ratio plus sector and size; candidate sparse panel with accession-aware working-capital features; advanced hierarchical accounting graph with semantic tag mapping and abstention. Estimate on rolling training windows, tune only validation, freeze holdout and cost assumptions. Build a no-action comparator when capacity uncertain. Primary risk: taxonomy changes, YTD versus quarter flows, acquisition effects, lookahead from amendments. No private data in repo.

## Proposed typed functions
load(as_of, source_ids)->versioned_rows; state(rows, cutoff)->xbrl-cash-conversion-reversal decision states; baseline(states)->actions; candidate(states, config)->actions; evaluate(actions, outcomes)->cash-flow MAE, tag mapping precision, forecast IC, coverage; validate() rejects YTD-to-quarter conversion, duplicate tag contexts, unit mismatch, 10-K/A future amendment. Map functions to REQ-001–004 and NFR-001/002; report missing inputs rather than fabricate. $90m research sleeve × 12 bps annual net benefit=$108k/year; no measured factor return. Check actual costs/available liquidity before shadow. No implementation yet.
