# PLAN — Cyber-Outage Contingent Repo Funding Recovery Routes
**Architecture:** public/approved adapters → versioned temporal contract → eligibility gate → costed baseline → Two-stage robust multi-commodity flow with cyber failure scenarios → causal/economic replay → human review.

## Source ingestion and data shape
Timestamped anonymized funding route uptime, fallback approvals, cutoff times, public OFR repo volumes/rates, synthetic outage schedules.
Event key: route × lender class × hourly outage scenario. Record original filing/publication alongside first local actionable market clock. OFR cleared rate/volume normally T+1 and tri-party T+2, so use public series as lagged calibration only; route outage telemetry must be timestamped pre-decision.
Integrate publicly identified records only after separate terms-of-use and granularity checks. Private data stay in private approved runtime.

## Implementable modules (proposed)
1. `contracts.py`: pydantic models for route × lender class × hourly outage scenario and immutable timestamps.
2. `sources.py`: rights-aware loader of ofrcyber, ofrrepo, secclose official references and separately licensed feeds.
3. `baseline.py`: Fixed 10% contingency funding buffer with one permitted fallback; must share opportunity universe and constraints with candidate.
4. `candidate.py`: Two-stage robust multi-commodity flow with cyber failure scenarios; add Distributionally robust scenario-tree route control with simultaneous correlated cash-lender disruptions only after ablation warrants complexity.
5. `feasibility.py`: x are route and lender allocation decisions, b is reserved liquidity, p_s is the unit shortfall penalty in outage scenario s; legal availability, committed limits and collateral eligibility bound x.
6. `evaluation.py`: metrics shortfall dollars, p95 duration, liquidity carry, fail probability, recovery cost, placebo, uncertainty and matched no-action baseline.
7. `report.py`: provenance and decision cost without asserting measured profitability.

## Identification challenges and alternatives
Public aggregates cannot recover the bank-level cash-lender network or prove an actual route is legally available. Use preregistered holdout splits, minimum economic materiality and delay-stressed baselines.
**Falsify:** Held-out synthetic/approved outage replay fails to reduce mean + tail shortfall at fixed total contingency cost.

## Delivery and rollback
Synthetic deterministic tests → available-at real-data audit → walk-forward/paired counterfactual → read-only shadow mode → human approval. Disable candidate on missing rights/clock or limit violation and revert to baseline. No code exists yet.
