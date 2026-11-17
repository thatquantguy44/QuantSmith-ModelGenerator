# Parameterized research prompt — Owner Co-Withdrawal Limits for Lendable Inventory

Use this prompt for a future documented research run, not as evidence that one occurred.

```text
Act as a researcher for US and European agency lending mandates.
Inputs: as_of={{AS_OF_UTC}}, decision_timezone={{IANA_TIMEZONE}},
universe_manifest={{UNIVERSE_PATH_AND_HASH}}, release_manifest={{SOURCE_PATH_AND_HASH}},
cost_config={{COST_CONFIG_PATH}}, risk_limits={{LIMITS_PATH}},
train_end={{TRAIN_END}}, validation_end={{VALIDATION_END}},
holdout_end={{HOLDOUT_END}}, seed={{SEED}}, mode={{PUBLIC_OR_PRIVATE_APPROVED}}.
Do not run if these inputs are unresolved. Do not invent values.
Decision: Cap loans supported by correlated sources and keep replacement options against simultaneous owner withdrawals.
Hypothesis: Tail co-withdrawal limits reduce 99th-percentile replacement cost by at least 15% versus owner-notional caps without sacrificing more than 2% normal lending revenue.
Target/grain: joint inventory-shortfall distribution and net cost of an allocation limit / owner x security x dated available-inventory snapshot.
Decision timing: Set next-day inventory limits after local close using confirmed availability received by cutoff; public fund holdings enter at filing acceptance, not portfolio as-of date. Never condition on the owner's future sale or recall notice.
Baseline: Static 10% owner concentration cap with independent withdrawal probabilities.
Candidate: Hierarchical common-factor withdrawal model and CVaR allocation; advanced optional: Distributionally robust copula stress allocation with mandate-group shocks.
Build common withdrawal factor, owner lineage groups and replacement tail scenarios. Enforce SPEC requirements and hard constraints.
Run negative test: Duplicate an owner under two IDs: effective diversification must not improve; simulate perfect co-withdrawal and verify the model does not report independent-source protection.
Gate: GO if 99th-percentile cost improves >=15%, normal net revenue loss <=2%, and at least 3 distinct withdrawal episodes are held out; STOP if dependence is unidentified or fewer than 24 months of owner histories exist.
Return source concentration limits and joint-withdrawal stress certificate, metrics, effective sample size, cost/capacity sensitivity,
all exclusions, source/claim ledger, reproducibility manifest and GO/STOP/BLOCKED.
Separate sourced facts, assumptions, calculations and hypotheses.
Do not trade, deploy, merge, send messages or expose private data.
```

No defaults silently enable live execution. If private inputs are absent, use synthetic fixtures only for code correctness and retain empirical state BLOCKED. Publication opportunity: High if dependence is identifiable; otherwise honest bounds on inventory diversification are useful internal research. A positive synthetic test cannot establish economic profitability.
