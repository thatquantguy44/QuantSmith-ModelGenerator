# PLAN — Collateral FX Mismatch Hedge under Margin Revaluation
**QMG-20261127-09 | A — Securities finance | USD/EUR/GBP securities finance | proposal only**
## Architecture
Source adapter → vintage/rights registry → collateral-fx-mismatch-hedge state builder → baseline → candidate → matched economic replay → independent gate. Grain: collateral basket × currency pair × margin day. Data: contract currency, collateral value, FX quotes, hedge instruments, margin frequency, hedge liquidity and constraints. Timing: only FX quotes/eligibility known before margin and hedge cutoff; hedge at next executable quote.

## Model sequence
Baseline static full currency hedge with same collateral and limits; candidate scenario expected-shortfall hedge sizing; advanced multi-period robust hedge with FX/collateral joint tails. Estimate on rolling training windows, tune only validation, freeze holdout and cost assumptions. Build a no-action comparator when capacity uncertain. Primary risk: hedges may not qualify as collateral or reduce regulatory haircut; joint FX/security tails unstable. No private data in repo.

## Proposed typed functions
load(as_of, source_ids)->versioned_rows; state(rows, cutoff)->collateral-fx-mismatch-hedge decision states; baseline(states)->actions; candidate(states, config)->actions; evaluate(actions, outcomes)->margin call ES, hedge slippage, capital/FX residual, hard constraints; validate() rejects FX gap, stale collateral quote, hedge illiquidity, mandatory haircut unchanged. Map functions to REQ-001–004 and NFR-001/002; report missing inputs rather than fabricate. $150m affected currency exposure × 8 bps annual risk-buffer cost reduction = $120k/year after hedge fees. Check actual costs/available liquidity before shadow. No implementation yet.
