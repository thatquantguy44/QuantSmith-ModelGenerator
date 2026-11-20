# PLAN — Global Shipping Connectivity Re-Routing to Inflation and Equity Margins
**Architecture:** public/approved adapters → versioned temporal contract → eligibility gate → costed baseline → Supply-route network exposure local projections → causal/economic replay → human review.

## Source ingestion and data shape
UNCTAD monthly/quarterly liner connectivity, MARAD freight/port dashboards, shipping rate indexes where licensed, CPI/PPI and issuer logistics costs.
Event key: country/port route × monthly index release × subsequent inflation/earnings outcome. Record original filing/publication alongside first local actionable market clock. UNCTAD latest confirmed index data update Sep 28 2026; a 2026-11-20 decision cannot use December data.
Integrate publicly identified records only after separate terms-of-use and granularity checks. Private data stay in private approved runtime.

## Implementable modules (proposed)
1. `contracts.py`: pydantic models for country/port route × monthly index release × subsequent inflation/earnings outcome and immutable timestamps.
2. `sources.py`: rights-aware loader of unctad, marad official references and separately licensed feeds.
3. `baseline.py`: Aggregate global shipping index versus region CPI with fixed lag; must share opportunity universe and constraints with candidate.
4. `candidate.py`: Supply-route network exposure local projections; add Causal graph shock transmission with endogenous alternative route capacity and measurement error only after ablation warrants complexity.
5. `feasibility.py`: r is importer region, p port corridor; shocks and alternate route count must use actually published index vintage.
6. `evaluation.py`: metrics inflation nowcast gain, equity margin dispersion, attribution stability and hedged net P&L, placebo, uncertainty and matched no-action baseline.
7. `report.py`: provenance and decision cost without asserting measured profitability.

## Identification challenges and alternatives
Connectivity is not real-time port congestion and quarterly updates can obscure freight cycle timing. Use preregistered holdout splits, minimum economic materiality and delay-stressed baselines.
**Falsify:** No incremental signal after global industrial production, oil and published trade volume controls.

## Delivery and rollback
Synthetic deterministic tests → available-at real-data audit → walk-forward/paired counterfactual → read-only shadow mode → human approval. Disable candidate on missing rights/clock or limit violation and revert to baseline. No code exists yet.
