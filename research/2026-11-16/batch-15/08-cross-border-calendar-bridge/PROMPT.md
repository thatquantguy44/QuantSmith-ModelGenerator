# Parameterized research prompt — Cross-Border Settlement Calendar Bridge Planner

Use this prompt for a future documented research run, not as evidence that one occurred.

```text
Act as a researcher for US, euro area and UK financing settlement.
Inputs: as_of={{AS_OF_UTC}}, decision_timezone={{IANA_TIMEZONE}},
universe_manifest={{UNIVERSE_PATH_AND_HASH}}, release_manifest={{SOURCE_PATH_AND_HASH}},
cost_config={{COST_CONFIG_PATH}}, risk_limits={{LIMITS_PATH}},
train_end={{TRAIN_END}}, validation_end={{VALIDATION_END}},
holdout_end={{HOLDOUT_END}}, seed={{SEED}}, mode={{PUBLIC_OR_PRIVATE_APPROVED}}.
Do not run if these inputs are unresolved. Do not invent values.
Decision: Choose an earlier settlement date and minimal bridge cash for already approved cross-border obligations.
Hypothesis: A service-specific dated-calendar planner eliminates at least 90% of calendar-caused exceptions and lowers bridge funding cost by 10% versus a fixed two-business-day prefunding rule.
Target/grain: bridge cash-days and avoidable calendar exceptions / obligation leg x settlement service x UTC instant.
Decision timing: Plan at least two local business days before a known holiday, using rules announced by then. Unexpected outages are separate stress scenarios; announced future changes enter only after their publication.
Baseline: Prefund every cross-border obligation two generic business days early, with manual holiday review.
Candidate: Time-expanded multi-service cash-flow network; advanced optional: Robust network flow with uncertain service extensions and intraday cash arrival bands.
Build service open intervals, version effective dates, cash-day gaps and DST conversion. Enforce SPEC requirements and hard constraints.
Run negative test: Replay US/Europe DST mismatch, Good Friday and a service-specific cutoff extension; the planner must distinguish securities and cash service availability.
Gate: GO if >=90% calendar exceptions avoided and >=10% net bridge-cost saving on >=24 holiday windows; zero infeasible settlement recommendations. STOP if routing assumptions require unapproved service access.
Return prefunding dates, minimal cash bridge and infeasible-leg alerts, metrics, effective sample size, cost/capacity sensitivity,
all exclusions, source/claim ledger, reproducibility manifest and GO/STOP/BLOCKED.
Separate sourced facts, assumptions, calculations and hypotheses.
Do not trade, deploy, merge, send messages or expose private data.
```

No defaults silently enable live execution. If private inputs are absent, use synthetic fixtures only for code correctness and retain empirical state BLOCKED. Publication opportunity: Medium: formal temporal service graph and reproducible operational errors; high practical portability. A positive synthetic test cannot establish economic profitability.
