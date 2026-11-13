# RUNTIME — Dynamic Currency-Hedge and Rebalancing Tax for Global Equity
**STATUS: proposed, NOT EXECUTABLE.** Any CLI below is a future interface contract.

## Entry point and input schema
`qmg.research.global_equity_dynamic_fx_hedge.cli`. Required JSON/YAML config fields:
```yaml
run_id: "synthetic-example-only"
as_of_utc: "YYYY-MM-DDTHH:MM:SSZ"
license_class: "public|licensed|restricted"
decision_time_utc: "YYYY-MM-DDTHH:MM:SSZ"
source_vintages: []
market_calendar: "approved-market-calendar"
train_start: "YYYY-MM-DD"
train_end: "YYYY-MM-DD"
holdout_start: "YYYY-MM-DD"
holdout_end: "YYYY-MM-DD"
random_seed: 123
risk_limits: {}
cost_model: {}
synthetic_only: true
```

## Future commands — do not run until code exists
```bash
python -m qmg.research.global_equity_dynamic_fx_hedge.cli validate --config configs/research-example.yaml
python -m qmg.research.global_equity_dynamic_fx_hedge.cli replay --config configs/research-example.yaml --synthetic-only
python -m qmg.research.global_equity_dynamic_fx_hedge.cli evaluate --config configs/research-example.yaml --holdout
```

## Runtime mathematical role
- Model objective: `min_(w,h) E[(R_equity(w)+R_FX(w,h)-target)^2] + λ*ES_95 + μ*turnover(w,h); 0≤h_c≤hmax_c`.
- Variables: w are country equity weights; h_c hedge fractions; ES_95 is expected shortfall; forward carry and bid/ask are charged at actual roll.
- Input contract: Country index total returns, currency spot/forward curves, FX liquidity, investability restrictions and funding rates.
- Cost, timing and capacity: rebalance at scheduled month-end using prior-close prices and then-available forward quotes; Limit to index futures/ETFs and deliverable/non-deliverable forward liquidity; enforce market access and capital controls.

## Future outputs (not generated)
`run_envelope.json` with source hashes/vintages/versions, `eligible_actions.json`, `baseline_metrics.json`, `candidate_metrics.json`, `confidence_intervals.json`, `claim_ledger.md`, `human_review.md`.

## Failure codes and operational controls
`SOURCE_UNLICENSED`, `FUTURE_INFORMATION`, `MISSING_VINTAGE`, `INVALID_UNIT`, `INFEASIBLE_CONSTRAINT`, `EXECUTION_UNAVAILABLE`, `NOT_IDENTIFIED`.
All errors fail closed with explicit reason; no fallback trading. Monitor source lag and policy drift; rollout and rollback require separate reviewed code/CI evidence.
