# RUNTIME — CFTC Positioning Concentration and Commodity Curve Convexity
**STATUS: proposed, NOT EXECUTABLE.** Any CLI below is a future interface contract.

## Entry point and input schema
`qmg.research.cot_crowding_curve_convexity.cli`. Required JSON/YAML config fields:
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
python -m qmg.research.cot_crowding_curve_convexity.cli validate --config configs/research-example.yaml
python -m qmg.research.cot_crowding_curve_convexity.cli replay --config configs/research-example.yaml --synthetic-only
python -m qmg.research.cot_crowding_curve_convexity.cli evaluate --config configs/research-example.yaml --holdout
```

## Runtime mathematical role
- Model objective: `Crowding_t=(spec_long_t-spec_short_t)/OI_t; Convexity_t=F1_t-2F2_t+F3_t; TailScore_t=β*Crowding_t*Convexity_t`.
- Variables: F1..F3 are aligned futures maturities with explicit roll rules; OI is the reported futures open interest, all at publication availability.
- Input contract: CFTC Disaggregated COT futures positions, futures contracts prices/rolls, EIA physical inventories where applicable.
- Cost, timing and capacity: earliest action is CFTC publication/next executable session; no use of Tuesday positions on Tuesday; Enforce futures open interest participation cap, roll liquidity and margin stress; no physical commodity positions.

## Future outputs (not generated)
`run_envelope.json` with source hashes/vintages/versions, `eligible_actions.json`, `baseline_metrics.json`, `candidate_metrics.json`, `confidence_intervals.json`, `claim_ledger.md`, `human_review.md`.

## Failure codes and operational controls
`SOURCE_UNLICENSED`, `FUTURE_INFORMATION`, `MISSING_VINTAGE`, `INVALID_UNIT`, `INFEASIBLE_CONSTRAINT`, `EXECUTION_UNAVAILABLE`, `NOT_IDENTIFIED`.
All errors fail closed with explicit reason; no fallback trading. Monitor source lag and policy drift; rollout and rollback require separate reviewed code/CI evidence.
