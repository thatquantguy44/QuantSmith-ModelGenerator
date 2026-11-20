# PLAN — Tokenized Treasury Collateral DvP Finality and Fallback Stress
**Architecture:** public/approved adapters → versioned temporal contract → eligibility gate → costed baseline → Timed Petri net state-machine model of mint/transfer/burn and escrow/finality rules → causal/economic replay → human review.

## Source ingestion and data shape
DTCC published service documentation, synthetic token mint-burn and conventional DvP events, validation proofs, cutoff windows and rehypothecation eligibility.
Event key: collateral lot × settlement leg × wallet/ledger state × timestamp. Record original filing/publication alongside first local actionable market clock. Use current production DTS service scope as of actual published date; planned 2027 integrations are NOT usable at a 2026 decision time.
Integrate publicly identified records only after separate terms-of-use and granularity checks. Private data stay in private approved runtime.

## Implementable modules (proposed)
1. `contracts.py`: pydantic models for collateral lot × settlement leg × wallet/ledger state × timestamp and immutable timestamps.
2. `sources.py`: rights-aware loader of dtcchub, dtcc2026, secclose official references and separately licensed feeds.
3. `baseline.py`: Conventional permitted book-entry DvP with settlement cutoff; must share opportunity universe and constraints with candidate.
4. `candidate.py`: Timed Petri net state-machine model of mint/transfer/burn and escrow/finality rules; add Formal model checking of cross-system DvP atomicity with stochastic disruption transitions only after ablation warrants complexity.
5. `feasibility.py`: r is a legally eligible path; require validated ownership, wallet permission, finality evidence, and a deterministic fallback if one leg fails.
6. `evaluation.py`: metrics liquidity-hours locked, failed atomicity scenarios, rollback time, eligible-settlement capacity, placebo, uncertainty and matched no-action baseline.
7. `report.py`: provenance and decision cost without asserting measured profitability.

## Identification challenges and alternatives
Token entitlements must not be treated as interchangeable with every conventional collateral/clearing agreement. Use preregistered holdout splits, minimum economic materiality and delay-stressed baselines.
**Falsify:** Cannot demonstrate legal/technical atomicity on synthetic fail-mid-transfer tests, or route fails to save liquidity net of controls.

## Delivery and rollback
Synthetic deterministic tests → available-at real-data audit → walk-forward/paired counterfactual → read-only shadow mode → human approval. Disable candidate on missing rights/clock or limit violation and revert to baseline. No code exists yet.
