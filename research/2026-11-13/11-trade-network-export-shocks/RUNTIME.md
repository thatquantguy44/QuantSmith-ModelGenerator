# RUNTIME — Trade-Network Export-Shock Transmission to Equity Sectors
**STATUS: proposed, NOT EXECUTABLE.** Any CLI below is a future interface contract.

## Entry point and input schema
`qmg.research.trade_network_export_shocks.cli`. Required JSON/YAML config fields:
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
python -m qmg.research.trade_network_export_shocks.cli validate --config configs/research-example.yaml
python -m qmg.research.trade_network_export_shocks.cli replay --config configs/research-example.yaml --synthetic-only
python -m qmg.research.trade_network_export_shocks.cli evaluate --config configs/research-example.yaml --holdout
```

## Runtime mathematical role
- Model objective: `Shock_(c,k,t)=Σ_p upstream_weight_(c,k,p)*Δexports_(p,t); alpha_(sector,t+h)=β*Shock_available_t - controls`.
- Variables: c is country, k sector, p harmonized product/trade edge, h a preselected post-publication investment horizon.
- Input contract: UN Comtrade reported and partner-reported trade by HS code/month; sector country revenue mix; FX; sector returns and macro controls.
- Cost, timing and capacity: monthly after trade report publication and revision; NEVER trade at reference-month timestamp; ETFs and liquid futures only for first implementation; portfolio turnover caps and country exposure floors.

## Future outputs (not generated)
`run_envelope.json` with source hashes/vintages/versions, `eligible_actions.json`, `baseline_metrics.json`, `candidate_metrics.json`, `confidence_intervals.json`, `claim_ledger.md`, `human_review.md`.

## Failure codes and operational controls
`SOURCE_UNLICENSED`, `FUTURE_INFORMATION`, `MISSING_VINTAGE`, `INVALID_UNIT`, `INFEASIBLE_CONSTRAINT`, `EXECUTION_UNAVAILABLE`, `NOT_IDENTIFIED`.
All errors fail closed with explicit reason; no fallback trading. Monitor source lag and policy drift; rollout and rollback require separate reviewed code/CI evidence.
