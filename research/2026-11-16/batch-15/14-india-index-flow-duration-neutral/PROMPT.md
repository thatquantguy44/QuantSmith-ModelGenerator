# Parameterized research prompt — India Bond Index-Flow Saturation

Use this prompt for a future documented research run, not as evidence that one occurred.

```text
Act as a researcher for India government bonds; emerging-market capital flows.
Inputs: as_of={{AS_OF_UTC}}, decision_timezone={{IANA_TIMEZONE}},
universe_manifest={{UNIVERSE_PATH_AND_HASH}}, release_manifest={{SOURCE_PATH_AND_HASH}},
cost_config={{COST_CONFIG_PATH}}, risk_limits={{LIMITS_PATH}},
train_end={{TRAIN_END}}, validation_end={{VALIDATION_END}},
holdout_end={{HOLDOUT_END}}, seed={{SEED}}, mode={{PUBLIC_OR_PRIVATE_APPROVED}}.
Do not run if these inputs are unresolved. Do not invent values.
Decision: Tilt duration-neutral eligible-versus-near-eligible government bond baskets using dated projected passive demand and realized foreign-flow saturation.
Hypothesis: Expected demand scaled by free-float turnover predicts inclusion-window residual returns better than an inclusion dummy, and improves net basket return by at least 20 bps per annum.
Target/grain: 20-session inclusion-window residual return and diminishing impact at high ownership / government bond x announcement/rebalance cohort x public flow release.
Decision timing: Act next Mumbai session after a verified inclusion announcement or ownership release; close at a predeclared post-effective window. Never use final index weights or future ownership before announcement.
Baseline: Equal-risk inclusion-event basket versus duration-matched eligible controls.
Candidate: Matched staggered event study with demand-pressure interactions; advanced optional: Doubly robust event design plus a structural price-impact saturation curve.
Build announced flow pressure, free-float turnover and lagged foreign ownership saturation. Enforce SPEC requirements and hard constraints.
Run negative test: Assign the same event to noneligible placebo bonds and to dates six months earlier; no persistent significant effect should survive cohort-level multiple-testing adjustment.
Gate: GO if >=20 net annualized bps improvement and event-cluster confidence lower bound >0; pretrends must pass a specified +/-10 bp equivalence band. STOP if fewer than 3 independent cohorts or ownership/AUM histories are reconstructed retrospectively.
Return event-study estimands, placebo diagnostics and duration-neutral research basket, metrics, effective sample size, cost/capacity sensitivity,
all exclusions, source/claim ledger, reproducibility manifest and GO/STOP/BLOCKED.
Separate sourced facts, assumptions, calculations and hypotheses.
Do not trade, deploy, merge, send messages or expose private data.
```

No defaults silently enable live execution. If private inputs are absent, use synthetic fixtures only for code correctness and retain empirical state BLOCKED. Publication opportunity: High identification interest; scarcity of independent cohorts could make a bounds/survey paper more credible than a causal alpha claim. A positive synthetic test cannot establish economic profitability.
