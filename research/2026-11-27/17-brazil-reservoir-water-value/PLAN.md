# PLAN — Brazil Reservoir Water Value and Utility Earnings Risk
**QMG-20261127-17 | B — Domestic/global markets | Brazil hydroelectric generation and utility equities | proposal only**
## Architecture
Source adapter → vintage/rights registry → brazil-reservoir-water-value state builder → baseline → candidate → matched economic replay → independent gate. Grain: ONS subsystem × day × release vintage. Data: stored energy, inflow, generation, load, thermal costs, transmission constraints, issuer contract exposures. Timing: only archived public release versions; ONS data may revise; forecast issuance known before decision.

## Model sequence
Baseline seasonal reservoir percentile and lagged marginal cost; candidate simplified stochastic dispatch LP; advanced multistage stochastic dual dynamic programming with hydrological scenarios. Estimate on rolling training windows, tune only validation, freeze holdout and cost assumptions. Build a no-action comparator when capacity uncertain. Primary risk: physical dispatch simplification, hydrology revision and issuer hedging obscure returns. No private data in repo.

## Proposed typed functions
load(as_of, source_ids)->versioned_rows; state(rows, cutoff)->brazil-reservoir-water-value decision states; baseline(states)->actions; candidate(states, config)->actions; evaluate(actions, outcomes)->marginal cost MAE, reliability, earnings scenario error, feasible dispatch; validate() rejects dry-year holdout, negative storage, future actual inflows, spill. Map functions to REQ-001–004 and NFR-001/002; report missing inputs rather than fabricate. $80m utility risk sleeve × 10 bps annual risk improvement=$80k/year; no physical dispatch authority. Check actual costs/available liquidity before shadow. No implementation yet.
