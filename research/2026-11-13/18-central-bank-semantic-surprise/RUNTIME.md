# RUNTIME — Central-Bank Communication Semantic Surprise Across Languages
**STATUS: proposed, NOT EXECUTABLE.** Any CLI below is a future interface contract.

## Entry point and input schema
`qmg.research.central_bank_semantic_surprise.cli`. Required JSON/YAML config fields:
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
python -m qmg.research.central_bank_semantic_surprise.cli validate --config configs/research-example.yaml
python -m qmg.research.central_bank_semantic_surprise.cli replay --config configs/research-example.yaml --synthetic-only
python -m qmg.research.central_bank_semantic_surprise.cli evaluate --config configs/research-example.yaml --holdout
```

## Runtime mathematical role
- Model objective: `Surprise_t = SentenceDistance(text_t, text_(t-1)) - ExpectedShift_t; alpha_(t+1)=β*Surprise_t, with abstention on low translation confidence`.
- Variables: text_t is official published statement as of event; ExpectedShift requires pre-event expectations and is omitted if unavailable rather than inferred ex post.
- Input contract: Versioned official policy statements; actual publication timestamps; pre-event interest rate futures; FX and rates price bars; translated text audit.
- Cost, timing and capacity: after official statement becomes public; never permit news articles, transcripts or price reactions from after decision in input; Only next-session liquid FX/rates futures; policy event size, slippage and gap risk explicitly costed.

## Future outputs (not generated)
`run_envelope.json` with source hashes/vintages/versions, `eligible_actions.json`, `baseline_metrics.json`, `candidate_metrics.json`, `confidence_intervals.json`, `claim_ledger.md`, `human_review.md`.

## Failure codes and operational controls
`SOURCE_UNLICENSED`, `FUTURE_INFORMATION`, `MISSING_VINTAGE`, `INVALID_UNIT`, `INFEASIBLE_CONSTRAINT`, `EXECUTION_UNAVAILABLE`, `NOT_IDENTIFIED`.
All errors fail closed with explicit reason; no fallback trading. Monitor source lag and policy drift; rollout and rollback require separate reviewed code/CI evidence.
