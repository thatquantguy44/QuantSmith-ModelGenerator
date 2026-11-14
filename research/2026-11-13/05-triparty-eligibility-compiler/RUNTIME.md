# RUNTIME — Tri-Party Collateral Eligibility Clause-to-Constraint Compiler
**STATUS: proposed, NOT EXECUTABLE.** Any CLI below is a future interface contract.

## Entry point and input schema
`qmg.research.triparty_eligibility_compiler.cli`. Required JSON/YAML config fields:
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
python -m qmg.research.triparty_eligibility_compiler.cli validate --config configs/research-example.yaml
python -m qmg.research.triparty_eligibility_compiler.cli replay --config configs/research-example.yaml --synthetic-only
python -m qmg.research.triparty_eligibility_compiler.cli evaluate --config configs/research-example.yaml --holdout
```

## Runtime mathematical role
- Model objective: `maximize Σ_(i,j) value_i*x_ij - substitution_cost_ij; x_ij<=eligible_ij; Σ_i exposure_ij<=limit_j`.
- Variables: x_ij is amount of asset i allocated to collateral agreement j; eligible_ij is verified legal rule, not an LLM prediction.
- Input contract: Synthetic collateral schedules; asset master; rating/issuer; eligibility categories; haircut tables; human-labeled clause examples.
- Cost, timing and capacity: rules valid at collateral decision; amendments apply from legal effective date, not document creation date; Can serve as quality-gate software without trading access; execution requires approved legal rules and certified contracts.

## Future outputs (not generated)
`run_envelope.json` with source hashes/vintages/versions, `eligible_actions.json`, `baseline_metrics.json`, `candidate_metrics.json`, `confidence_intervals.json`, `claim_ledger.md`, `human_review.md`.

## Failure codes and operational controls
`SOURCE_UNLICENSED`, `FUTURE_INFORMATION`, `MISSING_VINTAGE`, `INVALID_UNIT`, `INFEASIBLE_CONSTRAINT`, `EXECUTION_UNAVAILABLE`, `NOT_IDENTIFIED`.
All errors fail closed with explicit reason; no fallback trading. Monitor source lag and policy drift; rollout and rollback require separate reviewed code/CI evidence.
