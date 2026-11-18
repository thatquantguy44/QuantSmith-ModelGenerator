# Parameterized research prompt — European Gas Storage Deliverability Hedge

Use this prompt for a future documented research run, not as evidence that one occurred.

```text
Act as a researcher for Germany, Netherlands, Italy and European gas hubs.
Inputs: as_of={{AS_OF_UTC}}, decision_timezone={{IANA_TIMEZONE}},
universe_manifest={{UNIVERSE_PATH_AND_HASH}}, release_manifest={{SOURCE_PATH_AND_HASH}},
cost_config={{COST_CONFIG_PATH}}, risk_limits={{LIMITS_PATH}},
train_end={{TRAIN_END}}, validation_end={{VALIDATION_END}},
holdout_end={{HOLDOUT_END}}, seed={{SEED}}, mode={{PUBLIC_OR_PRIVATE_APPROVED}}.
Do not run if these inputs are unresolved. Do not invent values.
Decision: Hedge winter peak gas-delivery risk using facility-level withdrawal constraints rather than national percent-full alone.
Hypothesis: A deliverability-weighted storage index reduces winter peak procurement CVaR by at least 10% versus a percent-full rule at equal average hedge cost.
Target/grain: winter peak procurement tail cost and deliverable MWh shortfall / storage facility x gas day x publication version.
Decision timing: Recompute after first verified daily publication; execute next liquid hub session with at least one-day lag when historical publication time is unknown. Revised storage values never replace first-release features.
Baseline: Hedge ratio proportional to national percent-full deficit relative to trailing seasonal average.
Candidate: Constrained physical storage network and linear hedge projection; advanced optional: Stochastic dynamic storage model with uncertain withdrawal curves and robust hub hedge allocation.
Build withdrawal headroom, gas-day inventory state and hub connectivity. Enforce SPEC requirements and hard constraints.
Run negative test: Create two facilities with identical percent-full and different withdrawal limits: shortage outputs must differ. Remove one interconnector and forbid unphysical gas flows.
Gate: GO if >=10% CVaR reduction at equal mean cost across >=5 winters including one held-out stressed winter; STOP if results reverse under plausible deliverability curves or cross-border restrictions.
Return deliverability risk index and constrained seasonal hedge weights, metrics, effective sample size, cost/capacity sensitivity,
all exclusions, source/claim ledger, reproducibility manifest and GO/STOP/BLOCKED.
Separate sourced facts, assumptions, calculations and hypotheses.
Do not trade, deploy, merge, send messages or expose private data.
```

No defaults silently enable live execution. If private inputs are absent, use synthetic fixtures only for code correctness and retain empirical state BLOCKED. Publication opportunity: High: physical deliverability versus headline inventory; falsifiable nonlinear constraints rather than another weather predictor. A positive synthetic test cannot establish economic profitability.
