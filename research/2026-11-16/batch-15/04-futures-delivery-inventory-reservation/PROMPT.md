# Parameterized research prompt — Treasury Futures Delivery Inventory Reservation

Use this prompt for a future documented research run, not as evidence that one occurred.

```text
Act as a researcher for United States; Treasury futures deliverable baskets and securities loans.
Inputs: as_of={{AS_OF_UTC}}, decision_timezone={{IANA_TIMEZONE}},
universe_manifest={{UNIVERSE_PATH_AND_HASH}}, release_manifest={{SOURCE_PATH_AND_HASH}},
cost_config={{COST_CONFIG_PATH}}, risk_limits={{LIMITS_PATH}},
train_end={{TRAIN_END}}, validation_end={{VALIDATION_END}},
holdout_end={{HOLDOUT_END}}, seed={{SEED}}, mode={{PUBLIC_OR_PRIVATE_APPROVED}}.
Do not run if these inputs are unresolved. Do not invent values.
Decision: Reserve eligible inventory for an existing futures short versus lending it, charging the marginal delivery-option opportunity cost.
Hypothesis: A delivery-option reserve beats a fixed percentage holdback by at least 2 bps of annualized affected inventory value, after replacement, lending and hedge costs.
Target/grain: net lending revenue plus delivery economics for a fixed pre-existing futures obligation / CUSIP x futures contract x observation timestamp.
Decision timing: Reserve at 15:00 America/Chicago using quotes available by 14:55 and current contract basket version; subsequent delivery notices are outcomes, never predictive features.
Baseline: Hold back 10% of eligible basket inventory and allocate remaining loans using current fees.
Candidate: Scenario dynamic programming for marginal delivery-option value; advanced optional: Least-squares Monte Carlo with joint cash/futures/repo scenarios and integer delivery sizing.
Build invoice value, basket eligibility and marginal delivery option shadow cost. Enforce SPEC requirements and hard constraints.
Run negative test: Freeze the basket to a single security: option-selection value must vanish; change conversion factor units and require invoice identity failure rather than silent rescaling.
Gate: GO if >=2 annualized bps saving over fixed holdback across >=8 delivery cycles, no missed delivery and positive benefit at twice observed transaction costs. STOP if gains depend on hindsight cheapest-to-deliver identity.
Return lendable face limits and delivery-feasibility certificate, metrics, effective sample size, cost/capacity sensitivity,
all exclusions, source/claim ledger, reproducibility manifest and GO/STOP/BLOCKED.
Separate sourced facts, assumptions, calculations and hypotheses.
Do not trade, deploy, merge, send messages or expose private data.
```

No defaults silently enable live execution. If private inputs are absent, use synthetic fixtures only for code correctness and retain empirical state BLOCKED. Publication opportunity: High: interaction of delivery options and lending availability; empirical claim requires licensed synchronized markets. A positive synthetic test cannot establish economic profitability.
