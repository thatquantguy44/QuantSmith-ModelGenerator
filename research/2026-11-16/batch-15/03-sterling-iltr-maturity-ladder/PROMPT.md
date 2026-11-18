# Parameterized research prompt — Sterling ILTR Auction Demand Smoothing

Use this prompt for a future documented research run, not as evidence that one occurred.

```text
Act as a researcher for United Kingdom; GBP central-bank secured liquidity.
Inputs: as_of={{AS_OF_UTC}}, decision_timezone={{IANA_TIMEZONE}},
universe_manifest={{UNIVERSE_PATH_AND_HASH}}, release_manifest={{SOURCE_PATH_AND_HASH}},
cost_config={{COST_CONFIG_PATH}}, risk_limits={{LIMITS_PATH}},
train_end={{TRAIN_END}}, validation_end={{VALIDATION_END}},
holdout_end={{HOLDOUT_END}}, seed={{SEED}}, mode={{PUBLIC_OR_PRIVATE_APPROVED}}.
Do not run if these inputs are unresolved. Do not invent values.
Decision: Distribute a fixed eligible reserve requirement across future ILTR auctions and collateral sets without assuming a strategic low bid improves the clearing price.
Hypothesis: Demand smoothing lowers all-in expected funding expense by at least 1 bp relative to a single-auction ladder while preserving liquidity coverage under adverse allocation outcomes.
Target/grain: cost of a reserve maturity ladder subject to stressed coverage / auction x collateral set x release version.
Decision timing: Use results only after public release; plan by 09:00 Europe/London before an operation using earlier operations and latest approved reserve forecast. Verify each current auction deadline before a live pilot.
Baseline: Equal weekly maturities with bids at independently approved maximum willingness-to-pay; compare a single-auction funding plan separately.
Candidate: Shape-constrained aggregate supply-curve estimation plus stochastic ladder optimization; advanced optional: Partially identified robust auction planning over a set of rival-demand curves.
Build clearing-spread intervals, reserve coverage and maturity bucket exposure. Enforce SPEC requirements and hard constraints.
Run negative test: Replace the estimated supply curve with a flat curve: the model must not claim auction-price savings from moving a price-taking bid.
Gate: GO if >=1 bp net annualized saving versus equal ladder in >=12 held-out operations and no stressed reserve shortfall. STOP if all plausible demand curves imply the same ladder or savings require underbidding actual willingness-to-pay.
Return auction cash-demand ladder with allocation sensitivity bounds, metrics, effective sample size, cost/capacity sensitivity,
all exclusions, source/claim ledger, reproducibility manifest and GO/STOP/BLOCKED.
Separate sourced facts, assumptions, calculations and hypotheses.
Do not trade, deploy, merge, send messages or expose private data.
```

No defaults silently enable live execution. If private inputs are absent, use synthetic fixtures only for code correctness and retain empirical state BLOCKED. Publication opportunity: High identification interest, conditional on transparent partial-identification bounds rather than a falsely recovered demand curve. A positive synthetic test cannot establish economic profitability.
