# Parameterized research prompt — US Municipal Call-Exercise Friction Surface

Use this prompt for a future documented research run, not as evidence that one occurred.

```text
Act as a researcher for United States tax-exempt callable municipal bonds.
Inputs: as_of={{AS_OF_UTC}}, decision_timezone={{IANA_TIMEZONE}},
universe_manifest={{UNIVERSE_PATH_AND_HASH}}, release_manifest={{SOURCE_PATH_AND_HASH}},
cost_config={{COST_CONFIG_PATH}}, risk_limits={{LIMITS_PATH}},
train_end={{TRAIN_END}}, validation_end={{VALIDATION_END}},
holdout_end={{HOLDOUT_END}}, seed={{SEED}}, mode={{PUBLIC_OR_PRIVATE_APPROVED}}.
Do not run if these inputs are unresolved. Do not invent values.
Decision: Choose between matched callable bonds using a calibrated call hazard and cash-flow stress rather than yield-to-worst alone.
Hypothesis: Issuer-friction call probabilities reduce one-year cash-flow forecast error by at least 15% versus deterministic first-economic-call exercise and improve net matched-bond selection by 15 bps per annum.
Target/grain: call timing distribution, cash-flow forecast error and duration-adjusted bond return / bond x call opportunity x public notice/financial filing event.
Decision timing: Use only disclosures disseminated by prior close; trade at next obtainable firm offer/bid with a one-session latency. A call notice must enter at publication, not retroactively at the optional call date.
Baseline: Exercise at first call date when modeled refunding savings exceed a fixed 3% threshold; compare yield-to-worst selection.
Candidate: Discrete-time survival model with economic refunding covariates; advanced optional: Hierarchical issuer stopping model with financing frictions and cash-flow scenario valuation.
Build refunding incentive, notice state, issuer friction and time-to-call. Enforce SPEC requirements and hard constraints.
Run negative test: Insert a public call notice after the prior-close cutoff: the model must not predict certainty before disclosure. A noncallable bond must have zero optional call hazard.
Gate: GO if >=15% cash-flow MAE reduction and >=15 net annualized bps on >=500 held-out call opportunities; STOP if trade-vs-quote bias or missing failed/uncalled bonds explains gains.
Return call probability surface, cash-flow distribution and duration-matched selection report, metrics, effective sample size, cost/capacity sensitivity,
all exclusions, source/claim ledger, reproducibility manifest and GO/STOP/BLOCKED.
Separate sourced facts, assumptions, calculations and hypotheses.
Do not trade, deploy, merge, send messages or expose private data.
```

No defaults silently enable live execution. If private inputs are absent, use synthetic fixtures only for code correctness and retain empirical state BLOCKED. Publication opportunity: High: exercise frictions and segmented fixed income; strong public-document reproducibility potential. A positive synthetic test cannot establish economic profitability.
