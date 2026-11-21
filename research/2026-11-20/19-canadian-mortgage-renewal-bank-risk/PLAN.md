# PLAN — Canadian Mortgage Renewal Cohorts to Bank Credit-Risk Dispersion
**Architecture:** public/approved adapters → versioned temporal contract → eligibility gate → costed baseline → Vintage-cohort mortgage reset microsimulation from public aggregates → causal/economic replay → human review.

## Source ingestion and data shape
Bank of Canada public mortgage balances/rates, staff renewal methodology, bank annual/quarterly mortgage disclosures, CAD rate and housing data.
Event key: Canadian mortgage cohort × monthly public release × bank quarterly filing. Record original filing/publication alongside first local actionable market clock. Use released monthly tables and historical market expectations before renewal; a 2025 note's projected 2026 payments are scenario assumptions, not observed outcomes.
Integrate publicly identified records only after separate terms-of-use and granularity checks. Private data stay in private approved runtime.

## Implementable modules (proposed)
1. `contracts.py`: pydantic models for Canadian mortgage cohort × monthly public release × bank quarterly filing and immutable timestamps.
2. `sources.py`: rights-aware loader of canada, canadanote official references and separately licensed feeds.
3. `baseline.py`: Bank loss sensitivity to national unemployment and policy rate alone; must share opportunity universe and constraints with candidate.
4. `candidate.py`: Vintage-cohort mortgage reset microsimulation from public aggregates; add Hierarchical hazard model linking repricing, prepayment and issuer loan-level exposures only after ablation warrants complexity.
5. `feasibility.py`: Balance is refinanceable exposure (public aggregate proxy initially), ECL expected credit loss; individual bank vintage mapping may be incomplete.
6. `evaluation.py`: metrics future loss forecast gain, bank-spread risk hedging, sensitivity to vintage assumptions, net hedging cost, placebo, uncertainty and matched no-action baseline.
7. `report.py`: provenance and decision cost without asserting measured profitability.

## Identification challenges and alternatives
Public aggregate cohorts do not identify each bank's borrower vintage distribution or underwriting quality. Use preregistered holdout splits, minimum economic materiality and delay-stressed baselines.
**Falsify:** No cross-bank predictive signal after public loan books and unemployment/rate controls, or estimates too wide to act on.

## Delivery and rollback
Synthetic deterministic tests → available-at real-data audit → walk-forward/paired counterfactual → read-only shadow mode → human approval. Disable candidate on missing rights/clock or limit violation and revert to baseline. No code exists yet.
