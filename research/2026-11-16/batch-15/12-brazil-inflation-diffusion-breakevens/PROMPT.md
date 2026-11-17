# Parameterized research prompt — Brazil Inflation Diffusion versus Breakeven Carry

Use this prompt for a future documented research run, not as evidence that one occurred.

```text
Act as a researcher for Brazil; local nominal and inflation-linked government bonds.
Inputs: as_of={{AS_OF_UTC}}, decision_timezone={{IANA_TIMEZONE}},
universe_manifest={{UNIVERSE_PATH_AND_HASH}}, release_manifest={{SOURCE_PATH_AND_HASH}},
cost_config={{COST_CONFIG_PATH}}, risk_limits={{LIMITS_PATH}},
train_end={{TRAIN_END}}, validation_end={{VALIDATION_END}},
holdout_end={{HOLDOUT_END}}, seed={{SEED}}, mode={{PUBLIC_OR_PRIVATE_APPROVED}}.
Do not run if these inputs are unresolved. Do not invent values.
Decision: Choose a DV01-neutral nominal-versus-inflation-linked bond overlay using released inflation breadth and survey dispersion.
Hypothesis: Inflation-breadth revisions and Focus dispersion improve next-quarter breakeven return forecasts by at least 10% squared-error reduction versus carry plus headline surprise, and add 20 annualized net bps at fixed risk.
Target/grain: 63-session DV01-neutral excess breakeven return net of mechanical carry / inflation release x survey public version x matched bond pair.
Decision timing: Trade no earlier than next Sao Paulo session after verified inflation and survey publication, with one-hour processing lag. Survey collection dates are never treated as public timestamps.
Baseline: Carry/roll plus headline inflation surprise using a fixed ridge regression and identical risk budget.
Candidate: Sparse distributed-lag regression with local-projection diagnostics; advanced optional: Bayesian inflation component state-space model with scenario-robust breakeven sizing.
Build released inflation diffusion, survey dispersion and known indexation carry. Enforce SPEC requirements and hard constraints.
Run negative test: Set nominal and linked yields to parallel shifts with no inflation shock: residual P&L must reflect declared duration mismatch, not be mislabeled inflation alpha.
Gate: GO if >=10% forecast MSE improvement and >=20 net annualized bps at unchanged risk with >=40 nonoverlapping quarterly outcomes; STOP if official component vintage or executable curve history cannot be established.
Return breakeven forecast, DV01 hedge and market-access gate, metrics, effective sample size, cost/capacity sensitivity,
all exclusions, source/claim ledger, reproducibility manifest and GO/STOP/BLOCKED.
Separate sourced facts, assumptions, calculations and hypotheses.
Do not trade, deploy, merge, send messages or expose private data.
```

No defaults silently enable live execution. If private inputs are absent, use synthetic fixtures only for code correctness and retain empirical state BLOCKED. Publication opportunity: High if public component vintages can be assembled; tests information diffusion separately from mechanical indexation. A positive synthetic test cannot establish economic profitability.
