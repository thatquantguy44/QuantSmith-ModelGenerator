# PLAN — Noncash Collateral Correlation-Cluster Haircut Controller
**Architecture:** public/approved adapters → versioned temporal contract → eligibility gate → costed baseline → Scenario CVaR optimization with issuer cluster caps → causal/economic replay → human review.

## Source ingestion and data shape
Approved collateral constituents, synthetic issuer cross-holdings, stressed factor returns, liquidation bid/ask, haircut and legal threshold.
Event key: collateral security × issuer cluster × loan exposure × as-of time. Record original filing/publication alongside first local actionable market clock. Apply only return histories, prices, group linkages and issuer memberships known at the decision timestamp.
Integrate publicly identified records only after separate terms-of-use and granularity checks. Private data stay in private approved runtime.

## Implementable modules (proposed)
1. `contracts.py`: pydantic models for collateral security × issuer cluster × loan exposure × as-of time and immutable timestamps.
2. `sources.py`: rights-aware loader of ofrrepo, bisfmi official references and separately licensed feeds.
3. `baseline.py`: Uniform issuer/asset-class static haircut; must share opportunity universe and constraints with candidate.
4. `candidate.py`: Scenario CVaR optimization with issuer cluster caps; add Distributionally robust ambiguity-set CVaR with wrong-way liquidity correlation only after ablation warrants complexity.
5. `feasibility.py`: h is haircut vector, alpha tolerated tail probability and cap issuer concentration; credit/legal eligibility are hard constraints.
6. `evaluation.py`: metrics shortfall ES, collateral usage, haircut turnover, stress exceptions, placebo, uncertainty and matched no-action baseline.
7. `report.py`: provenance and decision cost without asserting measured profitability.

## Identification challenges and alternatives
Asset covariance may break exactly when haircuts are needed and public free-float proxies omit liquidation controls. Use preregistered holdout splits, minimum economic materiality and delay-stressed baselines.
**Falsify:** Risk benefit disappears when using stressed-correlation holdouts or violates legal haircut floors.

## Delivery and rollback
Synthetic deterministic tests → available-at real-data audit → walk-forward/paired counterfactual → read-only shadow mode → human approval. Disable candidate on missing rights/clock or limit violation and revert to baseline. No code exists yet.
