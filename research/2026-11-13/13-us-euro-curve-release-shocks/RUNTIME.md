# RUNTIME — US–Euro Sovereign Curve Shock Decomposition with Data Vintages
**STATUS: proposed, NOT EXECUTABLE.** Any CLI below is a future interface contract.

## Entry point and input schema
`qmg.research.us_euro_curve_release_shocks.cli`. Required JSON/YAML config fields:
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
python -m qmg.research.us_euro_curve_release_shocks.cli validate --config configs/research-example.yaml
python -m qmg.research.us_euro_curve_release_shocks.cli replay --config configs/research-example.yaml --synthetic-only
python -m qmg.research.us_euro_curve_release_shocks.cli evaluate --config configs/research-example.yaml --holdout
```

## Runtime mathematical role
- Model objective: `Δy_US,t = β1*Surprise_US,t + β2*Surprise_EU,t + u_t; h*=argmin_h E[(ΔP_US+h*ΔP_EU)^2]+turnover_cost(h)`.
- Variables: y is sovereign yield; Surprise is actual release minus consensus known beforehand (consensus may require licensing); h is DV01-scaled hedge.
- Input contract: ECB published euro yield curve, US yields and ALFRED macro vintages, official release times, FX hedges, rates futures cost.
- Cost, timing and capacity: end-of-release or next-session decision after releases disseminate; avoid falsely assuming instant access to revised series; Restrict first pass to liquid Treasury/Bund futures and realistic FX basis and futures trading costs.

## Future outputs (not generated)
`run_envelope.json` with source hashes/vintages/versions, `eligible_actions.json`, `baseline_metrics.json`, `candidate_metrics.json`, `confidence_intervals.json`, `claim_ledger.md`, `human_review.md`.

## Failure codes and operational controls
`SOURCE_UNLICENSED`, `FUTURE_INFORMATION`, `MISSING_VINTAGE`, `INVALID_UNIT`, `INFEASIBLE_CONSTRAINT`, `EXECUTION_UNAVAILABLE`, `NOT_IDENTIFIED`.
All errors fail closed with explicit reason; no fallback trading. Monitor source lag and policy drift; rollout and rollback require separate reviewed code/CI evidence.
