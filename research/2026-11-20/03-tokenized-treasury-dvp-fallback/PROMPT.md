# PROMPT — Tokenized Treasury Collateral DvP Finality and Fallback Stress
**Reusable parameterized agent prompt. Not an executed analysis.**
```text
ROLE: institutional skeptical quant research agent
RESEARCH_ID: QMG-20261120-03
MARKET: US Treasury collateral, DTC-tokenized entitlements and conventional settlement
DECISION: Select permitted collateral settlement pathway with provable delivery-versus-payment, finality and fail-safe fallback.
PROBLEM: Tokenized entitlements introduce chain/wallet/finality distinctions not present in ordinary book-entry Treasury repo workflow.
TESTABLE_H1: A permissioned DvP route with explicit finality state and contingency transfer reduces stress settlement lockup against conventional-only or optimistic atomic-claim baselines.
AS_OF_UTC: {{AS_OF_UTC}}
APPROVED_SOURCES: {{SOURCE_IDS_WITH_RIGHTS}}
RISK_LIMITS: {{ELIGIBILITY_AND_LIMITS}}
TRAIN_START / TRAIN_END: {{TRAIN_START}} / {{TRAIN_END}}
HOLDOUT_START / HOLDOUT_END: {{TEST_START}} / {{TEST_END}}
MARKET_CALENDAR: {{CALENDAR}}
COST_MODEL: {{COST_MODEL}}
OBSERVATION_GRAIN: collateral lot × settlement leg × wallet/ledger state × timestamp
FORMULATION: min_r E[LockedLiquidityHours_r*FundingRate + FailedSettlementCost_r + ReversionCost_r]
VARIABLES_AND_CONSTRAINTS: r is a legally eligible path; require validated ownership, wallet permission, finality evidence, and a deterministic fallback if one leg fails.
BASELINE: Conventional permitted book-entry DvP with settlement cutoff
CANDIDATE: Timed Petri net state-machine model of mint/transfer/burn and escrow/finality rules
ADVANCED_RESEARCH: Formal model checking of cross-system DvP atomicity with stochastic disruption transitions
METRICS: liquidity-hours locked, failed atomicity scenarios, rollback time, eligible-settlement capacity
FALSIFICATION: Cannot demonstrate legal/technical atomicity on synthetic fail-mid-transfer tests, or route fails to save liquidity net of controls.
REQUIRED_SAFETY: no future/revised as-of inputs, no confidential facts, no invented citations or empirical returns, no execution or autonomy.
OUTPUT: source claims with dates, data schema, mathematical derivation, synthetic edge cases, reproducible comparator, possible ablations, withheld holdout result IF actually computed, negative outcome discussion, rights blockers and human review request.
If code/data/rights unavailable label result BLOCKED, not PASS.
```
Read AGENT.md for tool authority and EVALS.md for negative controls.
