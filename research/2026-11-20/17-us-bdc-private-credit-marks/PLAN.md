# PLAN — Public BDC Portfolio Fair-Value Markdown Lead Indicator
**Architecture:** public/approved adapters → versioned temporal contract → eligibility gate → costed baseline → Issuer-level mark-hazard panel with censored holdings and missing-not-at-random controls → causal/economic replay → human review.

## Source ingestion and data shape
Original SEC BDC 10-Q/10-K investment schedules and mark values, sector classification, publicly known credit outcomes and licensed leveraged-loan pricing.
Event key: BDC filing × portfolio company/sector × disclosure timestamp. Record original filing/publication alongside first local actionable market clock. Use filed investment schedules only after filing acceptance; amendments/revised portfolio marks cannot enter historical quarters.
Integrate publicly identified records only after separate terms-of-use and granularity checks. Private data stay in private approved runtime.

## Implementable modules (proposed)
1. `contracts.py`: pydantic models for BDC filing × portfolio company/sector × disclosure timestamp and immutable timestamps.
2. `sources.py`: rights-aware loader of secapi, secfiling official references and separately licensed feeds.
3. `baseline.py`: BDC aggregate NAV discount and published nonaccrual percentage; must share opportunity universe and constraints with candidate.
4. `candidate.py`: Issuer-level mark-hazard panel with censored holdings and missing-not-at-random controls; add Hierarchical Bayesian marked-to-market credit migration model with portfolio network dependence only after ablation warrants complexity.
5. `feasibility.py`: PriceToCost is reported fair value over cost, nonaccrual flags only as filed, FundLag is filing delay; target is future externally validated credit deterioration.
6. `evaluation.py`: metrics future credit-event AUC/PR, mark-calibration error, NAV stress accuracy, opportunity capacity, placebo, uncertainty and matched no-action baseline.
7. `report.py`: provenance and decision cost without asserting measured profitability.

## Identification challenges and alternatives
BDC portfolio company identities, valuation methods and distressed sales are not uniformly disclosed; matching bias. Use preregistered holdout splits, minimum economic materiality and delay-stressed baselines.
**Falsify:** No improvement over current NAV discount/nonaccrual baseline in later quarters or effects only known after financial reports.

## Delivery and rollback
Synthetic deterministic tests → available-at real-data audit → walk-forward/paired counterfactual → read-only shadow mode → human approval. Disable candidate on missing rights/clock or limit violation and revert to baseline. No code exists yet.
