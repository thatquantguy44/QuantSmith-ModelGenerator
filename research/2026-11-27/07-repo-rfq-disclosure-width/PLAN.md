# PLAN — Repo RFQ Disclosure-Width versus Execution Competition
**QMG-20261127-07 | A — Securities finance | US and UK institutional repo | proposal only**
## Architecture
Source adapter → vintage/rights registry → repo-rfq-disclosure-width state builder → baseline → candidate → matched economic replay → independent gate. Grain: RFQ × recipient-count assignment × session. Data: RFQ timestamps, eligible recipients, executable responses, trade cost, approved randomization assignment and later price drift. Timing: assign before outreach; only historical availability and quote freshness; observe outcomes later.

## Model sequence
Baseline fixed approved number of recipients; candidate randomized experiment and heterogeneous treatment effects; advanced constrained contextual bandit only after randomized support and approval. Estimate on rolling training windows, tune only validation, freeze holdout and cost assumptions. Build a no-action comparator when capacity uncertain. Primary risk: interference across simultaneous RFQs and confidential order exposure; observational comparisons biased. No private data in repo.

## Proposed typed functions
load(as_of, source_ids)->versioned_rows; state(rows, cutoff)->repo-rfq-disclosure-width decision states; baseline(states)->actions; candidate(states, config)->actions; evaluate(actions, outcomes)->all-in cost, fill probability, post-RFQ drift, coverage and latency; validate() rejects assignment imbalance; correlated RFQs; non-executable response; unsupported recipient. Map functions to REQ-001–004 and NFR-001/002; report missing inputs rather than fabricate. $1bn annual average financed balance equivalent × 1.5 bps net savings = $150k/year; include leakage and message costs. Check actual costs/available liquidity before shadow. No implementation yet.
