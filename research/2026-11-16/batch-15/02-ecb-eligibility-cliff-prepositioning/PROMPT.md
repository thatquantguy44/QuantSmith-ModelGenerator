# Parameterized research prompt — ECB Collateral Eligibility-Cliff Prepositioning

Use this prompt for a future documented research run, not as evidence that one occurred.

```text
Act as a researcher for Euro area; EUR marketable collateral.
Inputs: as_of={{AS_OF_UTC}}, decision_timezone={{IANA_TIMEZONE}},
universe_manifest={{UNIVERSE_PATH_AND_HASH}}, release_manifest={{SOURCE_PATH_AND_HASH}},
cost_config={{COST_CONFIG_PATH}}, risk_limits={{LIMITS_PATH}},
train_end={{TRAIN_END}}, validation_end={{VALIDATION_END}},
holdout_end={{HOLDOUT_END}}, seed={{SEED}}, mode={{PUBLIC_OR_PRIVATE_APPROVED}}.
Do not run if these inputs are unresolved. Do not invent values.
Decision: Preposition replacement assets before an announced effective date while charging carry, haircut and transfer costs.
Hypothesis: A versioned effective-date planner lowers replacement expense by at least 2 annualized basis points on affected balances versus replacing at the deadline, with no use of information before announcement.
Target/grain: replacement implementation cost and eligible-value shortfall / ISIN x release version x effective date.
Decision timing: Evaluate after verified ECB publication and ingestion, with a minimum 30-minute operational latency; any action is next eligible settlement window. Historical daily snapshots without timestamp proof are usable only with a conservative next-business-day decision lag.
Baseline: Replace only at maturity or first effective ineligibility date using cheapest currently eligible asset.
Candidate: Rolling-horizon linear allocation using announced eligibility transitions; advanced optional: Distributionally robust prepositioning under uncertain unannounced eligibility loss.
Build announced future eligibility matrix, haircut-adjusted coverage and replacement ladder. Enforce SPEC requirements and hard constraints.
Run negative test: Move an announcement after the decision timestamp: all corresponding anticipatory trades must disappear; maturity may remain predictable from previously published terms.
Gate: GO if cost saving >=2 annualized bps on affected balances and zero eligibility violations across >=20 independent transition clusters; worst stress shortfall no larger than baseline. STOP if timestamp-safe sample is inadequate or cost rises under doubled bid/ask.
Return dated replacement schedule and coverage stress certificate, metrics, effective sample size, cost/capacity sensitivity,
all exclusions, source/claim ledger, reproducibility manifest and GO/STOP/BLOCKED.
Separate sourced facts, assumptions, calculations and hypotheses.
Do not trade, deploy, merge, send messages or expose private data.
```

No defaults silently enable live execution. If private inputs are absent, use synthetic fixtures only for code correctness and retain empirical state BLOCKED. Publication opportunity: Medium-high: event-time collateral option value, with public framework changes and transparent effective-time tests. A positive synthetic test cannot establish economic profitability.
