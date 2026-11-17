# Parameterized research prompt — South African Power Reliability Equity Exposure

Use this prompt for a future documented research run, not as evidence that one occurred.

```text
Act as a researcher for South Africa; JSE industrials, retailers and exporters.
Inputs: as_of={{AS_OF_UTC}}, decision_timezone={{IANA_TIMEZONE}},
universe_manifest={{UNIVERSE_PATH_AND_HASH}}, release_manifest={{SOURCE_PATH_AND_HASH}},
cost_config={{COST_CONFIG_PATH}}, risk_limits={{LIMITS_PATH}},
train_end={{TRAIN_END}}, validation_end={{VALIDATION_END}},
holdout_end={{HOLDOUT_END}}, seed={{SEED}}, mode={{PUBLIC_OR_PRIVATE_APPROVED}}.
Do not run if these inputs are unresolved. Do not invent values.
Decision: Build a sector/beta-neutral equity hedge against power-supply deterioration using pre-disclosed operational exposure.
Hypothesis: Exposure-weighted unplanned generation losses explain cash-flow/return sensitivity beyond national load-shedding stage, improving an outage hedge's downside loss by at least 10%.
Target/grain: power-shock residual equity sensitivity and hedge downside error / firm x day and dated generation/outage release.
Decision timing: Update after verified Eskom publication; act next JSE session with prior-disclosed firm exposures. Never label realized electricity usage as known before earnings disclosure.
Baseline: National load-shedding stage interacted with fixed sector averages and a market/FX hedge.
Candidate: Panel fixed effects with pre-period exposure interactions and event-placebo tests; advanced optional: Hierarchical causal sensitivity bounds plus constrained cash-flow hedge portfolio.
Build pre-disclosed energy intensity, backup coverage and released outage innovation. Enforce SPEC requirements and hard constraints.
Run negative test: Use a future outage series as a placebo and randomize exposure labels within sectors; the real-time pipeline must reject future features and significance should vanish under label randomization.
Gate: GO if downside hedge error improves >=10%, coefficient sign is stable in held-out periods and net benefit survives doubled spreads; STOP causal interpretation if pretrends or commodity/FX confounds remain.
Return firm sensitivity bounds and neutral power-risk hedge research basket, metrics, effective sample size, cost/capacity sensitivity,
all exclusions, source/claim ledger, reproducibility manifest and GO/STOP/BLOCKED.
Separate sourced facts, assumptions, calculations and hypotheses.
Do not trade, deploy, merge, send messages or expose private data.
```

No defaults silently enable live execution. If private inputs are absent, use synthetic fixtures only for code correctness and retain empirical state BLOCKED. Publication opportunity: High if exposure and timing can be made public and causal limits are respected; a careful negative result is valuable. A positive synthetic test cannot establish economic profitability.
