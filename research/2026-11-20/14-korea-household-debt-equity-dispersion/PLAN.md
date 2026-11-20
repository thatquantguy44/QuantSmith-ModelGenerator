# PLAN — Korean Household Debt-Service Shock to Bank–Consumer Equity Spread
**Architecture:** public/approved adapters → versioned temporal contract → eligibility gate → costed baseline → Panel local projections with shrinkage and sector time fixed effects → causal/economic replay → human review.

## Source ingestion and data shape
BIS Korea household DSR, BOK/Statistics Korea public lending/rates, issuer earnings and local equity returns, reporting vintage.
Event key: quarterly DSR release × issuer × accounting period × price timestamp. Record original filing/publication alongside first local actionable market clock. BIS Korean DSR published with quarterly lag (available through 2026-Q1 on checked dataset page); do not trade on 2026-Q2 unless publicly released.
Integrate publicly identified records only after separate terms-of-use and granularity checks. Private data stay in private approved runtime.

## Implementable modules (proposed)
1. `contracts.py`: pydantic models for quarterly DSR release × issuer × accounting period × price timestamp and immutable timestamps.
2. `sources.py`: rights-aware loader of koreabis official references and separately licensed feeds.
3. `baseline.py`: Equal-beta long banks short consumer discretionary with lagged policy-rate signal; must share opportunity universe and constraints with candidate.
4. `candidate.py`: Panel local projections with shrinkage and sector time fixed effects; add Dynamic heterogeneous household credit impulse response with instrumented policy-rate shocks only after ablation warrants complexity.
5. `feasibility.py`: b bank peer basket, c consumer peer basket, h disclosure-to-outcome window; DSRSurprise uses real-time expected vs published DSR, not revised future panels.
6. `evaluation.py`: metrics cross-sector earnings forecast delta, beta-neutral IR, worst-regime drawdown, capacity after local spreads, placebo, uncertainty and matched no-action baseline.
7. `report.py`: provenance and decision cost without asserting measured profitability.

## Identification challenges and alternatives
Endogenous rate policy and sector composition cause confounding; public issuer histories need delisting continuity. Use preregistered holdout splits, minimum economic materiality and delay-stressed baselines.
**Falsify:** No stable expected-earnings or beta-neutral sector difference once rates and economy factors are controlled.

## Delivery and rollback
Synthetic deterministic tests → available-at real-data audit → walk-forward/paired counterfactual → read-only shadow mode → human approval. Disable candidate on missing rights/clock or limit violation and revert to baseline. No code exists yet.
