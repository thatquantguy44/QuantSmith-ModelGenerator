# Parameterized research prompt — Repo Benchmark Outage and Revision Risk Monitor

Use this prompt for a future documented research run, not as evidence that one occurred.

```text
Act as a researcher for United States overnight secured funding.
Inputs: as_of={{AS_OF_UTC}}, decision_timezone={{IANA_TIMEZONE}},
universe_manifest={{UNIVERSE_PATH_AND_HASH}}, release_manifest={{SOURCE_PATH_AND_HASH}},
cost_config={{COST_CONFIG_PATH}}, risk_limits={{LIMITS_PATH}},
train_end={{TRAIN_END}}, validation_end={{VALIDATION_END}},
holdout_end={{HOLDOUT_END}}, seed={{SEED}}, mode={{PUBLIC_OR_PRIVATE_APPROVED}}.
Do not run if these inputs are unresolved. Do not invent values.
Decision: Choose whether a funding-risk report may use a published rate, show an uncertainty interval, or require manual review; never replace a contractual fallback.
Hypothesis: A publication-state monitor lowers material funding-risk reporting errors by at least 50% versus blindly carrying the last rate, with false escalation on fewer than 2% of ordinary releases.
Target/grain: reporting error and escalation burden under delayed/corrected publication / reference rate x publication event x revision version.
Decision timing: Snapshot at 08:15 America/New_York and again after verified revisions; only information received by each timestamp is usable. A 14:30 revision must not overwrite the morning feature snapshot.
Baseline: Carry the most recent official rate and mark missing releases only after end of day.
Candidate: Versioned publication-state rules plus robust short-horizon rate interval; advanced optional: Regime-switching Bayesian filtering with missing-source stress and calibrated selective reporting.
Build rate release age, version chain, contingency flag and interval width. Enforce SPEC requirements and hard constraints.
Run negative test: Hide a morning release and reveal a later correction: morning output must stay immutable and explicitly uncertain; no synthetic estimate may populate a contractual-rate field.
Gate: GO if >=50% reduction in material (>2 bp monitoring error) incidents and <2% false escalation over >=250 releases plus synthetic outages; interval coverage >=99%. STOP if rare-event evidence cannot separate improvement from excessive review.
Return accept/interval/review status, immutable as-of report and official-source pointer, metrics, effective sample size, cost/capacity sensitivity,
all exclusions, source/claim ledger, reproducibility manifest and GO/STOP/BLOCKED.
Separate sourced facts, assumptions, calculations and hypotheses.
Do not trade, deploy, merge, send messages or expose private data.
```

No defaults silently enable live execution. If private inputs are absent, use synthetic fixtures only for code correctness and retain empirical state BLOCKED. Publication opportunity: Medium: benchmark-data resilience and reproducible counterfactual outages; rare events limit generalization. A positive synthetic test cannot establish economic profitability.
