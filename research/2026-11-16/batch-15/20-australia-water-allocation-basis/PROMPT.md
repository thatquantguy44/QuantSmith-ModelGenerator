# Parameterized research prompt — Australian Water Allocation Shadow Price and Crop Basis

Use this prompt for a future documented research run, not as evidence that one occurred.

```text
Act as a researcher for Murray-Darling Basin, Australia; water allocations and agricultural exposure.
Inputs: as_of={{AS_OF_UTC}}, decision_timezone={{IANA_TIMEZONE}},
universe_manifest={{UNIVERSE_PATH_AND_HASH}}, release_manifest={{SOURCE_PATH_AND_HASH}},
cost_config={{COST_CONFIG_PATH}}, risk_limits={{LIMITS_PATH}},
train_end={{TRAIN_END}}, validation_end={{VALIDATION_END}},
holdout_end={{HOLDOUT_END}}, seed={{SEED}}, mode={{PUBLIC_OR_PRIVATE_APPROVED}}.
Do not run if these inputs are unresolved. Do not invent values.
Decision: Choose regional agricultural exposure or a crop-futures hedge only when released water scarcity changes affect a documented crop budget and survive basis costs.
Hypothesis: Allocation-decision surprises and transfer-constrained water shadow prices improve regional crop-margin forecasts by at least 10% versus seasonal water availability, and reduce hedge downside error by 5% net of costs.
Target/grain: regional crop-margin forecast and hedge basis-adjusted downside loss / water zone x allocation release x reported trade and crop season.
Decision timing: Update only after verified allocation announcement; water transaction price enters at public reporting time, not settlement/trade date. Trade a hedge no earlier than next liquid session; use seasons as independent split units.
Baseline: Seasonal allocation-volume score with a fixed regional crop basket and constant futures hedge ratio.
Candidate: Constrained crop-water optimization with allocation-shock local projections; advanced optional: Stochastic water/crop dynamic program and robust partial hedge across transfer zones.
Build announced allocation innovation, transfer-zone shadow price and crop-water budget. Enforce SPEC requirements and hard constraints.
Run negative test: Give identical aggregate water to two disconnected zones: optimization must retain different shadow prices; delaying trade reporting must move its first eligible feature date.
Gate: GO if margin MAE improves >=10% and net hedge downside loss >=5% across >=8 independently held-out seasons/zones; STOP if publication lag eliminates signal or local scarcity has no stable tradable crop exposure.
Return crop-margin scenario, local water shadow price and hedge-basis feasibility verdict, metrics, effective sample size, cost/capacity sensitivity,
all exclusions, source/claim ledger, reproducibility manifest and GO/STOP/BLOCKED.
Separate sourced facts, assumptions, calculations and hypotheses.
Do not trade, deploy, merge, send messages or expose private data.
```

No defaults silently enable live execution. If private inputs are absent, use synthetic fixtures only for code correctness and retain empirical state BLOCKED. Publication opportunity: High interdisciplinary potential, but weak tradable hedge linkage makes this an intentionally lower-priority contrarian project. A positive synthetic test cannot establish economic profitability.
