# Parameterized research prompt — Stock-Loan Repricing Bands with Relationship Friction

Use this prompt for a future documented research run, not as evidence that one occurred.

```text
Act as a researcher for United States and developed-Europe equity loans.
Inputs: as_of={{AS_OF_UTC}}, decision_timezone={{IANA_TIMEZONE}},
universe_manifest={{UNIVERSE_PATH_AND_HASH}}, release_manifest={{SOURCE_PATH_AND_HASH}},
cost_config={{COST_CONFIG_PATH}}, risk_limits={{LIMITS_PATH}},
train_end={{TRAIN_END}}, validation_end={{VALIDATION_END}},
holdout_end={{HOLDOUT_END}}, seed={{SEED}}, mode={{PUBLIC_OR_PRIVATE_APPROVED}}.
Do not run if these inputs are unresolved. Do not invent values.
Decision: Choose a fee-change threshold and batching cadence for existing loans rather than repricing every observed basis-point move.
Hypothesis: A two-sided repricing band increases net relationship-adjusted revenue by at least 5% versus daily benchmark matching without reducing risk-adjusted balances by more than 2%.
Target/grain: incremental net fee dollars minus message labor and attrition loss / loan x repricing proposal/response event.
Decision timing: Review at 10:00 local market time with benchmark releases and acknowledgments available by 09:55. Use an effective fee only after both contractual acceptance and booking; no retroactive filled proposals.
Baseline: Match yesterday's observable benchmark daily, with contractual limits; also compare a fixed 10-bp band.
Candidate: Impulse-control dynamic program with survival-calibrated borrower exits; advanced optional: Hierarchical Bayesian partially observed control with conservative policy evaluation.
Build fee gap, duration in band, response propensity and net processing cost. Enforce SPEC requirements and hard constraints.
Run negative test: Set negotiation and exit costs to zero: the optimal inaction band should collapse under an otherwise frictionless model; rejected proposals must never become realized fees.
Gate: GO if >=5% net revenue improvement with bootstrap lower bound >0 and balance loss <=2% in a pre-registered eligible cohort; no subgroup >5% deterioration. STOP if benefit relies on unobserved rejected requests or violates agreed repricing rights.
Return hold/reprice recommendation, approved band and counterfactual uncertainty, metrics, effective sample size, cost/capacity sensitivity,
all exclusions, source/claim ledger, reproducibility manifest and GO/STOP/BLOCKED.
Separate sourced facts, assumptions, calculations and hypotheses.
Do not trade, deploy, merge, send messages or expose private data.
```

No defaults silently enable live execution. If private inputs are absent, use synthetic fixtures only for code correctness and retain empirical state BLOCKED. Publication opportunity: Medium-high: measurable market-design frictions and interpretable control boundaries. A positive synthetic test cannot establish economic profitability.
