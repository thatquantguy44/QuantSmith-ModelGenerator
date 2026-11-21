# PLAN — Wheat Export Inspection Revisions to Global Basis and Calendar Spreads
**Architecture:** public/approved adapters → versioned temporal contract → eligibility gate → costed baseline → Mixed-frequency distributed-lag export surprise model → causal/economic replay → human review.

## Source ingestion and data shape
USDA AMS export grain inspections dashboard, USDA wheat supply/price tables, official crop calendars, futures curves and export policy announcement records.
Event key: weekly USDA inspection release × grain class × destination × exchange quote timestamp. Record original filing/publication alongside first local actionable market clock. USDA dashboard launched Oct 14 2026 and wheat tables updated Nov 12 2026; do not replace historic reports with latest annual revisions.
Integrate publicly identified records only after separate terms-of-use and granularity checks. Private data stay in private approved runtime.

## Implementable modules (proposed)
1. `contracts.py`: pydantic models for weekly USDA inspection release × grain class × destination × exchange quote timestamp and immutable timestamps.
2. `sources.py`: rights-aware loader of usdagrain, wheat official references and separately licensed feeds.
3. `baseline.py`: Monthly seasonal wheat spread regression using last known WASDE; must share opportunity universe and constraints with candidate.
4. `candidate.py`: Mixed-frequency distributed-lag export surprise model; add Structural Bayesian crop-flow network with regional stock constraints and censoring only after ablation warrants complexity.
5. `feasibility.py`: r region; expected inspections estimated using only pre-release history; h is post-release decision horizon with realistic market access.
6. `evaluation.py`: metrics spread forecast delta, regional basis tracking, net slippage-adjusted hedge P&L, regime robustness, placebo, uncertainty and matched no-action baseline.
7. `report.py`: provenance and decision cost without asserting measured profitability.

## Identification challenges and alternatives
Weekly inspections differ from actual export commitments; Black Sea supply and policy announcements may dominate. Use preregistered holdout splits, minimum economic materiality and delay-stressed baselines.
**Falsify:** No predictive improvement after weather, futures calendar effects and contemporaneous official release lags.

## Delivery and rollback
Synthetic deterministic tests → available-at real-data audit → walk-forward/paired counterfactual → read-only shadow mode → human approval. Disable candidate on missing rights/clock or limit violation and revert to baseline. No code exists yet.
