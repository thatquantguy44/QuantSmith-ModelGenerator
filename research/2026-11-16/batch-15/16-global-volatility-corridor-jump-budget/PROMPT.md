# Parameterized research prompt — US–Europe Corridor Variance and Jump-Risk Budget

Use this prompt for a future documented research run, not as evidence that one occurred.

```text
Act as a researcher for US S&P 500 and euro-area equity index options.
Inputs: as_of={{AS_OF_UTC}}, decision_timezone={{IANA_TIMEZONE}},
universe_manifest={{UNIVERSE_PATH_AND_HASH}}, release_manifest={{SOURCE_PATH_AND_HASH}},
cost_config={{COST_CONFIG_PATH}}, risk_limits={{LIMITS_PATH}},
train_end={{TRAIN_END}}, validation_end={{VALIDATION_END}},
holdout_end={{HOLDOUT_END}}, seed={{SEED}}, mode={{PUBLIC_OR_PRIVATE_APPROVED}}.
Do not run if these inputs are unresolved. Do not invent values.
Decision: Allocate a limited short-corridor-variance risk budget across US and European indices while purchasing a defined tail hedge.
Hypothesis: A corridor/jump-aware allocation reduces 99% tail loss by at least 15% at equal net carry versus equal-vega short-variance with the same tail-hedge budget.
Target/grain: net option-strip carry and stress/tail loss at fixed hedge premium / market x option expiry/strike x quote instant plus intraday underlying bars.
Decision timing: Allocate at a common UTC snapshot when both markets have liquid executable quotes; use prior completed return bars only. Do not pair a European close with later US data as contemporaneous.
Baseline: Equal-vega option-strip variance exposure by market with a fixed put-spread tail hedge and identical costs.
Candidate: Semiparametric continuous/jump decomposition and constrained risk-budget allocation; advanced optional: Distributionally robust jump-diffusion option-portfolio optimization.
Build corridor variance, overnight jump proxies, executable strip costs and tail hedge Greeks. Enforce SPEC requirements and hard constraints.
Run negative test: Insert a large overnight gap with no intraday prints: loss and jump exposure must remain visible; an apparent free option caused by zero/stale bid must be rejected.
Gate: GO if >=15% ES reduction with mean net carry within 5% of baseline across >=8 years including held-out stress; STOP if benefit fails under doubled option spreads or cannot be implemented by listed strips.
Return vega allocation, explicit option-strip positions and stress funding requirements, metrics, effective sample size, cost/capacity sensitivity,
all exclusions, source/claim ledger, reproducibility manifest and GO/STOP/BLOCKED.
Separate sourced facts, assumptions, calculations and hypotheses.
Do not trade, deploy, merge, send messages or expose private data.
```

No defaults silently enable live execution. If private inputs are absent, use synthetic fixtures only for code correctness and retain empirical state BLOCKED. Publication opportunity: High methodological potential; a crowded literature means exact corridor and jump novelty needs further review. A positive synthetic test cannot establish economic profitability.
