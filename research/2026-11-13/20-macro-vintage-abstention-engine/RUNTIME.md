# RUNTIME — Macro-Vintage Integrity Engine with Prediction Abstention
**STATUS: proposed, NOT EXECUTABLE.** Any CLI below is a future interface contract.

## Entry point and input schema
`qmg.research.macro_vintage_abstention_engine.cli`. Required JSON/YAML config fields:
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
python -m qmg.research.macro_vintage_abstention_engine.cli validate --config configs/research-example.yaml
python -m qmg.research.macro_vintage_abstention_engine.cli replay --config configs/research-example.yaml --synthetic-only
python -m qmg.research.macro_vintage_abstention_engine.cli evaluate --config configs/research-example.yaml --holdout
```

## Runtime mathematical role
- Model objective: `Trade_t=1{E[utility(signal_t)|vintage_quality_t] > cost_t and quality_t>=q_min}; otherwise hold benchmark`.
- Variables: quality measures source reliability, revision uncertainty, coverage and release history; expected utility estimated strictly from past vintages.
- Input contract: ALFRED historical revisions, ECB yield releases, OECD SDMX data vintage calendars, US/global market proxies.
- Cost, timing and capacity: update only after first verified public release; revisions must enter as new events, not retroactively; Primarily a reusable research data-quality service; alpha/executable returns need licensed market backtest.

## Future outputs (not generated)
`run_envelope.json` with source hashes/vintages/versions, `eligible_actions.json`, `baseline_metrics.json`, `candidate_metrics.json`, `confidence_intervals.json`, `claim_ledger.md`, `human_review.md`.

## Failure codes and operational controls
`SOURCE_UNLICENSED`, `FUTURE_INFORMATION`, `MISSING_VINTAGE`, `INVALID_UNIT`, `INFEASIBLE_CONSTRAINT`, `EXECUTION_UNAVAILABLE`, `NOT_IDENTIFIED`.
All errors fail closed with explicit reason; no fallback trading. Monitor source lag and policy drift; rollout and rollback require separate reviewed code/CI evidence.
