# Parameterized research prompt — Collateral Stale-Mark Quarantine and Conservative Valuation

Use this prompt for a future documented research run, not as evidence that one occurred.

```text
Act as a researcher for US and euro-area secured financing collateral.
Inputs: as_of={{AS_OF_UTC}}, decision_timezone={{IANA_TIMEZONE}},
universe_manifest={{UNIVERSE_PATH_AND_HASH}}, release_manifest={{SOURCE_PATH_AND_HASH}},
cost_config={{COST_CONFIG_PATH}}, risk_limits={{LIMITS_PATH}},
train_end={{TRAIN_END}}, validation_end={{VALIDATION_END}},
holdout_end={{HOLDOUT_END}}, seed={{SEED}}, mode={{PUBLIC_OR_PRIVATE_APPROVED}}.
Do not run if these inputs are unresolved. Do not invent values.
Decision: Quarantine a suspect mark or assign a conservative valuation interval, escalating exceptions rather than automatically altering contractual marks.
Hypothesis: A cross-source temporal-consistency gate reduces unsecured-value underestimation by at least 30% versus last-price carry-forward at an operational false-quarantine rate below 1%.
Target/grain: underestimated unsecured exposure and false quarantine burden / collateral instrument x mark source x quote/receive event.
Decision timing: Gate each mark at ingestion before its use in a financing solve; reference marks must be received earlier than the current solve. Labels are adjudications collected later and assigned only to future model training windows.
Baseline: Use latest received price within a fixed one-day age limit; otherwise last valid mark with static buffer.
Candidate: Robust cross-source median and asset-specific age/interval rule; advanced optional: State-space price filtering with conformal lower valuation bounds and selective quarantine.
Build source age, price convention residual, lineage overlap and conservative interval. Enforce SPEC requirements and hard constraints.
Run negative test: Inject a 100x currency/unit error, stale timestamp, ex-coupon drop and two nominally independent marks with identical upstream provenance; detect unit/staleness defects while preserving valid convention changes.
Gate: GO if underestimation falls >=30%, clean-mark false quarantine <1%, and lower-bound coverage >=99% in stress replay; reject if benefit comes only from excessive haircuts or review burden exceeds 0.5 FTE per 10k instruments.
Return mark status, safe monitoring valuation, lineage warning and escalation reason, metrics, effective sample size, cost/capacity sensitivity,
all exclusions, source/claim ledger, reproducibility manifest and GO/STOP/BLOCKED.
Separate sourced facts, assumptions, calculations and hypotheses.
Do not trade, deploy, merge, send messages or expose private data.
```

No defaults silently enable live execution. If private inputs are absent, use synthetic fixtures only for code correctness and retain empirical state BLOCKED. Publication opportunity: Medium: reproducible error taxonomy and dependence-aware coverage; strongest value may be operational rather than journal novelty. A positive synthetic test cannot establish economic profitability.
