# PLAN — CCP Default-Fund Mutualization Marginal Risk Budget
**Architecture:** public/approved adapters → versioned temporal contract → eligibility gate → costed baseline → Transparent worst-two-member default waterfall simulator → causal/economic replay → human review.

## Source ingestion and data shape
Public CPMI/IOSCO disclosure framework, synthetic member default distributions, concentration factors, CCP product eligibility and fee schedules.
Event key: CCP membership × cleared product × default stress scenario. Record original filing/publication alongside first local actionable market clock. Use published CCP rulebooks and dated quantitative disclosures only when released; past final stress reports cannot enter historical decisions early.
Integrate publicly identified records only after separate terms-of-use and granularity checks. Private data stay in private approved runtime.

## Implementable modules (proposed)
1. `contracts.py`: pydantic models for CCP membership × cleared product × default stress scenario and immutable timestamps.
2. `sources.py`: rights-aware loader of bisfmi, secclose official references and separately licensed feeds.
3. `baseline.py`: Exposure limit proportional to initial margin only; must share opportunity universe and constraints with candidate.
4. `candidate.py`: Transparent worst-two-member default waterfall simulator; add Coherent-risk allocation via Shapley/gradient ES under correlated default network scenarios only after ablation warrants complexity.
5. `feasibility.py`: j clearing membership or CCP, s default scenario, alpha stress-tail quantile; actual waterfall order and limits are CCP specific.
6. `evaluation.py`: metrics tail capital charge, stress shortfall, liquidity buffer usage, net clearing benefit, placebo, uncertainty and matched no-action baseline.
7. `report.py`: provenance and decision cost without asserting measured profitability.

## Identification challenges and alternatives
Actual default fund contributions and replenishment terms may differ from public examples and vary by venue. Use preregistered holdout splits, minimum economic materiality and delay-stressed baselines.
**Falsify:** No material differentiation in conditional tail loss versus margin-only limits after conservative parameter uncertainty.

## Delivery and rollback
Synthetic deterministic tests → available-at real-data audit → walk-forward/paired counterfactual → read-only shadow mode → human approval. Disable candidate on missing rights/clock or limit violation and revert to baseline. No code exists yet.
