# Parameterized research prompt — Japan Buyback Completion Credibility

Use this prompt for a future documented research run, not as evidence that one occurred.

```text
Act as a researcher for Japan listed equities; developed-market event research.
Inputs: as_of={{AS_OF_UTC}}, decision_timezone={{IANA_TIMEZONE}},
universe_manifest={{UNIVERSE_PATH_AND_HASH}}, release_manifest={{SOURCE_PATH_AND_HASH}},
cost_config={{COST_CONFIG_PATH}}, risk_limits={{LIMITS_PATH}},
train_end={{TRAIN_END}}, validation_end={{VALIDATION_END}},
holdout_end={{HOLDOUT_END}}, seed={{SEED}}, mode={{PUBLIC_OR_PRIVATE_APPROVED}}.
Do not run if these inputs are unresolved. Do not invent values.
Decision: Weight an announcement-event equity sleeve by ex-ante completion probability rather than headline authorized buyback size.
Hypothesis: Completion-weighted signals improve 60-trading-day sector/beta-neutral net returns by at least 50 bps per annum versus authorization-size signals, after 30 bps round-trip costs.
Target/grain: program completion probability and 60-day residual equity return / issuer x announced buyback program x filing acceptance event.
Decision timing: Enter at next Tokyo session VWAP after a public announcement plus 30 minutes processing; filings arriving after the next-open cutoff shift another session. Completion reports update only when publicly filed.
Baseline: Authorization divided by contemporaneously known float market cap, with the same neutral portfolio and execution rules.
Candidate: Calibrated discrete-time completion hazard with constrained event portfolio; advanced optional: Joint competing-risk completion/cancellation model and doubly robust announcement event analysis.
Build prior completion rate, cash-funded capacity, expiry horizon and free-float-normalized authorization. Enforce SPEC requirements and hard constraints.
Run negative test: Shift completion filings to their reporting-period end: leakage checker must reject the join; include terminated programs and delisted issuers with zero future authorization assumed.
Gate: GO if completion Brier improves >=10% and net return uplift >=50 annualized bps with block-bootstrap lower bound >0 over >=200 programs and a held-out year; STOP on missing delistings or gains concentrated in inaccessible prints.
Return completion probabilities and neutral event-sleeve research orders, metrics, effective sample size, cost/capacity sensitivity,
all exclusions, source/claim ledger, reproducibility manifest and GO/STOP/BLOCKED.
Separate sourced facts, assumptions, calculations and hypotheses.
Do not trade, deploy, merge, send messages or expose private data.
```

No defaults silently enable live execution. If private inputs are absent, use synthetic fixtures only for code correctness and retain empirical state BLOCKED. Publication opportunity: High: completion credibility and execution mechanism heterogeneity; causal claims require stronger identification than prediction. A positive synthetic test cannot establish economic profitability.
