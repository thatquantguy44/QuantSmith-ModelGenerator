# PLAN — Swiss Franc Conditional Safe-Haven Hedge Reliability
**QMG-20261127-13 | B — Domestic/global markets | Switzerland, euro area and global risk portfolios | proposal only**
## Architecture
Source adapter → vintage/rights registry → chf-safe-haven-state state builder → baseline → candidate → matched economic replay → independent gate. Grain: currency pair × day × decision timestamp. Data: CHF exchange rates, policy rates, risk factors, global equity returns, executable FX hedge quotes. Timing: daily decisions after all required markets close, execute next quote; no revised intervention data.

## Model sequence
Baseline fixed CHF allocation with equal carry budget; candidate threshold quantile regression on risk-state proxies; advanced hidden Markov state model with robust scenario hedge. Estimate on rolling training windows, tune only validation, freeze holdout and cost assumptions. Build a no-action comparator when capacity uncertain. Primary risk: safe-haven relation unstable; overlapping global closes and intervention confounding. No private data in repo.

## Proposed typed functions
load(as_of, source_ids)->versioned_rows; state(rows, cutoff)->chf-safe-haven-state decision states; baseline(states)->actions; candidate(states, config)->actions; evaluate(actions, outcomes)->expected shortfall, carry, hedge hit rate, turnover; validate() rejects crisis placebo, asynchronous close, stale rate, one-event dominance. Map functions to REQ-001–004 and NFR-001/002; report missing inputs rather than fabricate. $200m risk budget × 4 bps annual hypothetical avoided hedging cost=$80k/year; tail-risk reduction not cash revenue unless monetized. Check actual costs/available liquidity before shadow. No implementation yet.
