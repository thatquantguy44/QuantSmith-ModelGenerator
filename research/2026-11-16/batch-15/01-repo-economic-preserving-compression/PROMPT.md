# Parameterized research prompt — Repo Compression with Cash-Flow Preservation

Use this prompt for a future documented research run, not as evidence that one occurred.

```text
Act as a researcher for US Treasury repo; one legal netting set at a time.
Inputs: as_of={{AS_OF_UTC}}, decision_timezone={{IANA_TIMEZONE}},
universe_manifest={{UNIVERSE_PATH_AND_HASH}}, release_manifest={{SOURCE_PATH_AND_HASH}},
cost_config={{COST_CONFIG_PATH}}, risk_limits={{LIMITS_PATH}},
train_end={{TRAIN_END}}, validation_end={{VALIDATION_END}},
holdout_end={{HOLDOUT_END}}, seed={{SEED}}, mode={{PUBLIC_OR_PRIVATE_APPROVED}}.
Do not run if these inputs are unresolved. Do not invent values.
Decision: Select existing tickets to tear up or resize without changing each participant's dated cash and CUSIP obligations.
Hypothesis: An economics-preserving compression reduces eligible gross ticket notional by at least 15% and operational cost by at least 10% versus bilateral pair cancellation, with no additional settlement or market risk.
Target/grain: retained gross notional and verified per-date cash/security conservation / repo ticket and dated cash/security obligation.
Decision timing: Freeze the ledger at 14:00 America/New_York; use only confirmed records ingested by 13:55 and decisions before the relevant service cutoff. Cash-flow amendments received later enter the next solve.
Baseline: Cancel exact opposite tickets bilaterally within a legal set; otherwise hold the original book.
Candidate: Mixed-integer minimum-cost circulation with exact cash-flow conservation; advanced optional: Robust multi-period compression with consent uncertainty and settlement-feasibility cuts.
Build dated incidence matrices, lot constraints and consent mask. Enforce SPEC requirements and hard constraints.
Run negative test: Construct a three-node cycle with mismatched maturity dates: it must remain uncompressed; changing one consent flag must remove every affected action.
Gate: GO only with >=15% gross reduction and >=10% realized operational cost reduction on held-out eligible sets; every cash/security residual <=$0.01 cash or zero security units; zero consent violations. STOP on any economic transfer or if gains vanish after legal filtering.
Return proposed tear-up/resizing schedule, exact flow certificate and rejected-action reasons, metrics, effective sample size, cost/capacity sensitivity,
all exclusions, source/claim ledger, reproducibility manifest and GO/STOP/BLOCKED.
Separate sourced facts, assumptions, calculations and hypotheses.
Do not trade, deploy, merge, send messages or expose private data.
```

No defaults silently enable live execution. If private inputs are absent, use synthetic fixtures only for code correctness and retain empirical state BLOCKED. Publication opportunity: Medium: constrained compression with dated multi-asset conservation; novelty relative to existing compression literature needs a dedicated review. A positive synthetic test cannot establish economic profitability.
