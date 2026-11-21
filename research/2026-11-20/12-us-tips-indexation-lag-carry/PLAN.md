# PLAN — US TIPS CPI Indexation-Lag Carry and Breakeven Calendar Surface
**Architecture:** public/approved adapters → versioned temporal contract → eligibility gate → costed baseline → Deterministic index-ratio accrual and liquidity-factor attribution → causal/economic replay → human review.

## Source ingestion and data shape
Treasury official daily TIPS index ratios/CPI, vintage BLS CPI, nominal/TIPS quotes, issue terms, accrued interest.
Event key: TIPS CUSIP × CPI/index-ratio effective date × decision timestamp. Record original filing/publication alongside first local actionable market clock. Daily index ratios can be forecast only from already published reference CPI; preserve first release and later corrections.
Integrate publicly identified records only after separate terms-of-use and granularity checks. Private data stay in private approved runtime.

## Implementable modules (proposed)
1. `contracts.py`: pydantic models for TIPS CUSIP × CPI/index-ratio effective date × decision timestamp and immutable timestamps.
2. `sources.py`: rights-aware loader of tips, secapi official references and separately licensed feeds.
3. `baseline.py`: Duration-matched TIPS-minus-nominal bond without CPI-calendar signal; must share opportunity universe and constraints with candidate.
4. `candidate.py`: Deterministic index-ratio accrual and liquidity-factor attribution; add State-space real/nominal curve with stochastic CPI surprise and inflation floor convexity only after ablation warrants complexity.
5. `feasibility.py`: KnownIndexAccrual_t is observable at decision time; carry, breakeven and real-yield exposures require duration scaling and deflation floors.
6. `evaluation.py`: metrics hedge tracking error, information ratio net of costs, index replication error, carry decomposition residual, placebo, uncertainty and matched no-action baseline.
7. `report.py`: provenance and decision cost without asserting measured profitability.

## Identification challenges and alternatives
Illiquid issue quotations, inflation floor optionality, unrevised CPI data and seasonality overfit. Use preregistered holdout splits, minimum economic materiality and delay-stressed baselines.
**Falsify:** Improvement vanishes versus a carry-only and time-matched duration hedge after execution spread costs.

## Delivery and rollback
Synthetic deterministic tests → available-at real-data audit → walk-forward/paired counterfactual → read-only shadow mode → human approval. Disable candidate on missing rights/clock or limit violation and revert to baseline. No code exists yet.
