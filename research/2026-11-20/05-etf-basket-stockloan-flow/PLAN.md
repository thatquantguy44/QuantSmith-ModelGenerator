# PLAN — ETF Creation/Redemption Basket Shock to Stock-Loan Supply
**Architecture:** public/approved adapters → versioned temporal contract → eligibility gate → costed baseline → Hierarchical event study with issuer-basket aggregation and controls → causal/economic replay → human review.

## Source ingestion and data shape
ETF disclosed holdings and creation units, public filings, official membership events, licensed AP basket/flows and loan availability for later study.
Event key: ETF × constituent × creation/redemption day × publication time. Record original filing/publication alongside first local actionable market clock. Only baskets available to a decision-maker before ETF order cutoff may be used; end-of-day holding reports are not morning baskets.
Integrate publicly identified records only after separate terms-of-use and granularity checks. Private data stay in private approved runtime.

## Implementable modules (proposed)
1. `contracts.py`: pydantic models for ETF × constituent × creation/redemption day × publication time and immutable timestamps.
2. `sources.py`: rights-aware loader of secapi, secfiling official references and separately licensed feeds.
3. `baseline.py`: Change in ETF shares outstanding plus index-event dummy; must share opportunity universe and constraints with candidate.
4. `candidate.py`: Hierarchical event study with issuer-basket aggregation and controls; add Instrumented flow shock model addressing ETF price-demand endogeneity only after ablation warrants complexity.
5. `feasibility.py`: i is CUSIP, h forecast horizon, basket delta is an appropriately signed and actually available in-kind constituent-flow measure; no lookahead custom basket files.
6. `evaluation.py`: metrics inventory forecast MAE, short availability calibration, incremental net inventory carry, execution slippage, placebo, uncertainty and matched no-action baseline.
7. `report.py`: provenance and decision cost without asserting measured profitability.

## Identification challenges and alternatives
Most executable AP basket details and actual stock-loan supply are not public. Use preregistered holdout splits, minimum economic materiality and delay-stressed baselines.
**Falsify:** No incremental held-out inventory signal after availability alignment and underlying stock flow controls.

## Delivery and rollback
Synthetic deterministic tests → available-at real-data audit → walk-forward/paired counterfactual → read-only shadow mode → human approval. Disable candidate on missing rights/clock or limit violation and revert to baseline. No code exists yet.
