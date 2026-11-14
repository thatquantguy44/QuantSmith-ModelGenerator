# RUNTIME — Corporate-Bond TRACE Liquidity-to-ETF NAV Stress Transmission
**STATUS: proposed, NOT EXECUTABLE.** Any CLI below is a future interface contract.

## Entry point and input schema
`qmg.research.credit_trace_etf_nav_dislocation.cli`. Required JSON/YAML config fields:
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
python -m qmg.research.credit_trace_etf_nav_dislocation.cli validate --config configs/research-example.yaml
python -m qmg.research.credit_trace_etf_nav_dislocation.cli replay --config configs/research-example.yaml --synthetic-only
python -m qmg.research.credit_trace_etf_nav_dislocation.cli evaluate --config configs/research-example.yaml --holdout
```

## Runtime mathematical role
- Model objective: `LiquidityDisp_t=Q90(trade_cost_bond,t)-Q10(trade_cost_bond,t); predict |ETFprice_t-NAVestimate_t| with quote-timing controls`.
- Variables: trade_cost_bond is valid time-matched cost proxy; NAVestimate is vendor methodology-specific, potentially stale and never treated as fillable.
- Input contract: FINRA TRACE public aggregate/trade pages, subscription historical bond records, ETF market prices, NAV timestamps, bond indices, CDX basis.
- Cost, timing and capacity: end-of-session / next-session ETF risk adjustment only; public aggregate data may not cover security-level historical panel; Only liquid ETFs and hedges, no synthetic bond execution assuming NAV arbitrage.

## Future outputs (not generated)
`run_envelope.json` with source hashes/vintages/versions, `eligible_actions.json`, `baseline_metrics.json`, `candidate_metrics.json`, `confidence_intervals.json`, `claim_ledger.md`, `human_review.md`.

## Failure codes and operational controls
`SOURCE_UNLICENSED`, `FUTURE_INFORMATION`, `MISSING_VINTAGE`, `INVALID_UNIT`, `INFEASIBLE_CONSTRAINT`, `EXECUTION_UNAVAILABLE`, `NOT_IDENTIFIED`.
All errors fail closed with explicit reason; no fallback trading. Monitor source lag and policy drift; rollout and rollback require separate reviewed code/CI evidence.
