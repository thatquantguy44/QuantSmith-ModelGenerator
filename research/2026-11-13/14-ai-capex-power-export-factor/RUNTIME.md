# RUNTIME — AI Infrastructure Capex-to-Power-and-Export Supply Chain Factor
**STATUS: proposed, NOT EXECUTABLE.** Any CLI below is a future interface contract.

## Entry point and input schema
`qmg.research.ai_capex_power_export_factor.cli`. Required JSON/YAML config fields:
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
python -m qmg.research.ai_capex_power_export_factor.cli validate --config configs/research-example.yaml
python -m qmg.research.ai_capex_power_export_factor.cli replay --config configs/research-example.yaml --synthetic-only
python -m qmg.research.ai_capex_power_export_factor.cli evaluate --config configs/research-example.yaml --holdout
```

## Runtime mathematical role
- Model objective: `Bottleneck_t = min(grid_capacity_t/expected_load_t, export_supply_t/needed_components_t); signal_i,t=exposure_i*(Bottleneck_t-1)`.
- Variables: expected_load and needed_components are explicit assumptions, not observable facts; no inferral of private company data-center locations.
- Input contract: SEC EDGAR filed capital expenditure and commitments, EIA power demand/generation, public utility service-area reports, UN Comtrade semiconductor/electrical equipment trade.
- Cost, timing and capacity: rebalance monthly after latest public filings, energy updates and international trade release; Cap exposure to liquid industry ETFs/stocks; forecast vintages and reasonable turnover restrictions.

## Future outputs (not generated)
`run_envelope.json` with source hashes/vintages/versions, `eligible_actions.json`, `baseline_metrics.json`, `candidate_metrics.json`, `confidence_intervals.json`, `claim_ledger.md`, `human_review.md`.

## Failure codes and operational controls
`SOURCE_UNLICENSED`, `FUTURE_INFORMATION`, `MISSING_VINTAGE`, `INVALID_UNIT`, `INFEASIBLE_CONSTRAINT`, `EXECUTION_UNAVAILABLE`, `NOT_IDENTIFIED`.
All errors fail closed with explicit reason; no fallback trading. Monitor source lag and policy drift; rollout and rollback require separate reviewed code/CI evidence.
