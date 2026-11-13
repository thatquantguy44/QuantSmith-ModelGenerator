# RUNTIME — Weather Forecast Revision as an Electricity-to-Gas Risk Hedge
**STATUS: proposed, NOT EXECUTABLE.** Any CLI below is a future interface contract.

## Entry point and input schema
`qmg.research.weather_electricity_gas_forecast_revisions.cli`. Required JSON/YAML config fields:
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
python -m qmg.research.weather_electricity_gas_forecast_revisions.cli validate --config configs/research-example.yaml
python -m qmg.research.weather_electricity_gas_forecast_revisions.cli replay --config configs/research-example.yaml --synthetic-only
python -m qmg.research.weather_electricity_gas_forecast_revisions.cli evaluate --config configs/research-example.yaml --holdout
```

## Runtime mathematical role
- Model objective: `Revision_r,t = LoadForecast_r,t^(latest issued) - LoadForecast_r,t^(prior issued); Hedge_t=clip(β*Revision_r,t,limits)`.
- Variables: r is power balancing authority; revisions use two immutable issue-time snapshots; hedge maps only to liquid related assets with modeled cross-basis.
- Input contract: NWS issued and archived forecasts, EIA balancing authority hourly load and generation, power/gas futures settlements and basis.
- Cost, timing and capacity: forecast issuance is the earliest legal decision; never consume later realized weather or EIA actual load before release; Trade via highly liquid gas futures or energy equity baskets, with geographic basis and sector beta mismatch priced.

## Future outputs (not generated)
`run_envelope.json` with source hashes/vintages/versions, `eligible_actions.json`, `baseline_metrics.json`, `candidate_metrics.json`, `confidence_intervals.json`, `claim_ledger.md`, `human_review.md`.

## Failure codes and operational controls
`SOURCE_UNLICENSED`, `FUTURE_INFORMATION`, `MISSING_VINTAGE`, `INVALID_UNIT`, `INFEASIBLE_CONSTRAINT`, `EXECUTION_UNAVAILABLE`, `NOT_IDENTIFIED`.
All errors fail closed with explicit reason; no fallback trading. Monitor source lag and policy drift; rollout and rollback require separate reviewed code/CI evidence.
