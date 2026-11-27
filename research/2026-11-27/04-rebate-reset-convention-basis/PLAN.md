# PLAN — Benchmark Reset Convention Basis in Securities Loan Rebates
**QMG-20261127-04 | A — Securities finance | USD and GBP cash-collateral lending | proposal only**
## Architecture
Source adapter → vintage/rights registry → rebate-reset-convention-basis state builder → baseline → candidate → matched economic replay → independent gate. Grain: contract × accrual date × fixing vintage. Data: rate benchmark vintages, executed convention text, spread, calendars, balance and asset accruals. Timing: fixings available only after publication; project unknown future rates as scenarios, never realized inputs.

## Model sequence
Baseline same-day benchmark with standard day count; candidate deterministic reset/compounding convention engine; advanced scenario curve and hedge sensitivity under competing reset clocks. Estimate on rolling training windows, tune only validation, freeze holdout and cost assumptions. Build a no-action comparator when capacity uncertain. Primary risk: ambiguous fallback language and publication lag; legacy terms not inferable from index name. No private data in repo.

## Proposed typed functions
load(as_of, source_ids)->versioned_rows; state(rows, cutoff)->rebate-reset-convention-basis decision states; baseline(states)->actions; candidate(states, config)->actions; evaluate(actions, outcomes)->reconciliation USD, residual basis, projected mismatch, fixture accuracy; validate() rejects weekend accrual, leap day, missing fixing, negative rate, different day counts. Map functions to REQ-001–004 and NFR-001/002; report missing inputs rather than fabricate. $500m average balance × 3 bps annual preventable basis = $150k/year; no speculative trading profits. Check actual costs/available liquidity before shadow. No implementation yet.
