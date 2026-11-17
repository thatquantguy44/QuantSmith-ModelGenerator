# Parameterized research prompt — US CMBS Refinance Hazard from Public Disclosures

Use this prompt for a future documented research run, not as evidence that one occurred.

```text
Act as a researcher for United States commercial property and securitized credit.
Inputs: as_of={{AS_OF_UTC}}, decision_timezone={{IANA_TIMEZONE}},
universe_manifest={{UNIVERSE_PATH_AND_HASH}}, release_manifest={{SOURCE_PATH_AND_HASH}},
cost_config={{COST_CONFIG_PATH}}, risk_limits={{LIMITS_PATH}},
train_end={{TRAIN_END}}, validation_end={{VALIDATION_END}},
holdout_end={{HOLDOUT_END}}, seed={{SEED}}, mode={{PUBLIC_OR_PRIVATE_APPROVED}}.
Do not run if these inputs are unresolved. Do not invent values.
Decision: Limit public CMBS/REIT credit exposure according to released refinance cash-flow gaps and competing maturity outcomes.
Hypothesis: A vintage-safe competing-risk model improves 12-month refinancing-distress Brier score by at least 10% versus maturity wall plus current DSCR and lowers stress portfolio loss by 5% at equal spread carry.
Target/grain: 12-month competing refinance outcomes and portfolio loss at fixed spread carry / loan x public reporting vintage x maturity/outcome event.
Decision timing: Update risk after SEC acceptance plus one business day parsing/review; a prior reporting month's NOI remains unavailable until filing. Amendments are appended and never rewrite earlier risk snapshots.
Baseline: Logistic distress model using months-to-maturity and last publicly available DSCR with fixed rate-shock scenarios.
Candidate: Competing-risk survival model with refinance cash-gap covariates; advanced optional: Hierarchical property-cycle hazard and cash-flow waterfall scenario optimization.
Build public refinance cash gap, maturity hazard and amendment lineage. Enforce SPEC requirements and hard constraints.
Run negative test: Replace an original loan maturity with a later extension and verify earlier features remain unchanged; include liquidated loans and enforce waterfall conservation under default scenarios.
Gate: GO if Brier improves >=10% and stress loss falls >=5% at same carry over a held-out issuance vintage; STOP if modification histories, exited loans or outcome timing are missing for >10% of sample.
Return competing-outcome probabilities, missing-field coverage and tranche mapping limits, metrics, effective sample size, cost/capacity sensitivity,
all exclusions, source/claim ledger, reproducibility manifest and GO/STOP/BLOCKED.
Separate sourced facts, assumptions, calculations and hypotheses.
Do not trade, deploy, merge, send messages or expose private data.
```

No defaults silently enable live execution. If private inputs are absent, use synthetic fixtures only for code correctness and retain empirical state BLOCKED. Publication opportunity: High: public disclosure vintages and competing refinancing paths; publication depends on reliable field extraction and sample representativeness. A positive synthetic test cannot establish economic profitability.
