# ROADMAP — Tokenized Treasury Collateral DvP Finality and Fallback Stress
**Phase 0: source and math validation (weeks 1–2).** Confirm US Treasury collateral, DTC-tokenized entitlements and conventional settlement, allowable decision Select permitted collateral settlement pathway with provable delivery-versus-payment, finality and fail-safe fallback., units in `min_r E[LockedLiquidityHours_r*FundingRate + FailedSettlementCost_r + ReversionCost_r]`, executable baseline and exact publication lag. **Gate:** legal/data entitlements and H0 agreed.

**Phase 1: synthetic engineering (weeks 3–4).** Implement typed collateral lot × settlement leg × wallet/ledger state × timestamp fixture, deterministic Conventional permitted book-entry DvP with settlement cutoff and source-vintage checksum. **Gate:** AC-001 and AC-002, fail-closed data access.

**Phase 2: empirical research (weeks 5–8).** If data licensed, compare Timed Petri net state-machine model of mint/transfer/burn and escrow/finality rules versus holdout baseline; optionally prototype Formal model checking of cross-system DvP atomicity with stochastic disruption transitions. **Gate:** Cannot demonstrate legal/technical atomicity on synthetic fail-mid-transfer tests, or route fails to save liquidity net of controls.

**Phase 3: robustness (weeks 9–12).** Stress Token entitlements must not be treated as interchangeable with every conventional collateral/clearing agreement.; evaluate liquidity-hours locked, failed atomicity scenarios, rollback time, eligible-settlement capacity, capacity, capital, transaction costs and estimation uncertainty. **Gate:** report both negative and positive scenarios.

**Phase 4: read-only shadow (conditional).** Human-reviewed monitoring and rollback, no automatic trading. **Current state:** no phase has started; schedule estimates are planning assumptions.
