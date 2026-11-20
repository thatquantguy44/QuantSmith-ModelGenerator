# PLAN — Asia–US Cross-Listed ADR Opening Auction Information Transfer
**Architecture:** public/approved adapters → versioned temporal contract → eligibility gate → costed baseline → State-space asynchronous Kalman fair-value update using futures and related peer prices → causal/economic replay → human review.

## Source ingestion and data shape
Issuer depositary receipts ratios, local listings, public filings, FX quote timestamps, US ADR opening auctions, dividends and corporate action history.
Event key: ADR × home-market session × US opening-auction timestamp. Record original filing/publication alongside first local actionable market clock. Prevent local-price forward fill across sessions; ratio/corporate actions must be known at the US quote decision time.
Integrate publicly identified records only after separate terms-of-use and granularity checks. Private data stay in private approved runtime.

## Implementable modules (proposed)
1. `contracts.py`: pydantic models for ADR × home-market session × US opening-auction timestamp and immutable timestamps.
2. `sources.py`: rights-aware loader of secfiling, secapi official references and separately licensed feeds.
3. `baseline.py`: Last home close × publicly known ADR conversion ratio × contemporaneous FX spot; must share opportunity universe and constraints with candidate.
4. `candidate.py`: State-space asynchronous Kalman fair-value update using futures and related peer prices; add Continuous-time latent-price discovery with joint jump and optimal execution inventory control only after ablation warrants complexity.
5. `feasibility.py`: Ratio_i is point-in-time ADR share ratio, FX has correct currency direction, CrossMarketNews is post-local close information known before US auction.
6. `evaluation.py`: metrics auction fair-value error, paired realized slippage, inventory risk, settlement/convertibility feasibility, placebo, uncertainty and matched no-action baseline.
7. `report.py`: provenance and decision cost without asserting measured profitability.

## Identification challenges and alternatives
ADR conversion fees, access restrictions, local holidays and stale home quotes create phantom arbitrage. Use preregistered holdout splits, minimum economic materiality and delay-stressed baselines.
**Falsify:** No consistent opening execution improvement after financing, foreign exchange, depositary and auction spread costs.

## Delivery and rollback
Synthetic deterministic tests → available-at real-data audit → walk-forward/paired counterfactual → read-only shadow mode → human approval. Disable candidate on missing rights/clock or limit violation and revert to baseline. No code exists yet.
