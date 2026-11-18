# Parameterized research prompt — Securities-Loan Dust-Lot Consolidation

Use this prompt for a future documented research run, not as evidence that one occurred.

```text
Act as a researcher for US and developed-market equity lending.
Inputs: as_of={{AS_OF_UTC}}, decision_timezone={{IANA_TIMEZONE}},
universe_manifest={{UNIVERSE_PATH_AND_HASH}}, release_manifest={{SOURCE_PATH_AND_HASH}},
cost_config={{COST_CONFIG_PATH}}, risk_limits={{LIMITS_PATH}},
train_end={{TRAIN_END}}, validation_end={{VALIDATION_END}},
holdout_end={{HOLDOUT_END}}, seed={{SEED}}, mode={{PUBLIC_OR_PRIVATE_APPROVED}}.
Do not run if these inputs are unresolved. Do not invent values.
Decision: Consolidate or close eligible small lots within the same owner/borrower/legal permissions while preserving economic exposure and service constraints.
Hypothesis: Integer cost-aware lot consolidation cuts recurring servicing expense by at least 20% relative to pro-rata allocation without reducing net lending revenue by more than 1%.
Target/grain: active-ticket count and net servicing-adjusted margin / owner x borrower x security loan lot x service day.
Decision timing: Solve after confirmed end-of-day books and before next-day instruction cutoff; only booked demand and valid consent known at solve time enter. Settled movements are later outcomes.
Baseline: Pro-rata eligible allocation across owners, subject to existing concentration caps.
Candidate: Fixed-charge transportation MILP; advanced optional: Multi-period lot consolidation with persistence penalties and uncertain demand bands.
Build fixed servicing charge, permitted owner-lot map and movement-cost matrix. Enforce SPEC requirements and hard constraints.
Run negative test: Set per-ticket cost to zero: consolidation must not invent savings; introduce an owner-specific nontransferability flag and verify its lot remains untouched.
Gate: GO if >=20% servicing-cost saving and <=1% net revenue loss, zero owner-rights violations and payback within 12 months on measured cost inputs. STOP if gains disappear after movement fees or permitted allocations are fixed.
Return consolidation suggestions with per-owner exposure/revenue reconciliation, metrics, effective sample size, cost/capacity sensitivity,
all exclusions, source/claim ledger, reproducibility manifest and GO/STOP/BLOCKED.
Separate sourced facts, assumptions, calculations and hypotheses.
Do not trade, deploy, merge, send messages or expose private data.
```

No defaults silently enable live execution. If private inputs are absent, use synthetic fixtures only for code correctness and retain empirical state BLOCKED. Publication opportunity: Medium: fixed-charge inventory allocation with fair attribution; production engineering likely more valuable than model novelty. A positive synthetic test cannot establish economic profitability.
