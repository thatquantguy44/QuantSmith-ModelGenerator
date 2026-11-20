# PLAN — EU ETS Auction Supply Revision and Carbon Futures Carry
**Architecture:** public/approved adapters → versioned temporal contract → eligibility gate → costed baseline → Event study of auction schedule revisions and futures risk factors → causal/economic replay → human review.

## Source ingestion and data shape
European Commission vintage auction calendars, Union Registry verified emissions/compliance, dated policy changes, EUA/power/gas contract prices.
Event key: EU ETS auction calendar publication × allowance futures tenor × exchange quote timestamp. Record original filing/publication alongside first local actionable market clock. 2027 auction schedule announced Jul 30 2026; 2025 compliance data public Oct 5 2026; only released data at as-of permitted.
Integrate publicly identified records only after separate terms-of-use and granularity checks. Private data stay in private approved runtime.

## Implementable modules (proposed)
1. `contracts.py`: pydantic models for EU ETS auction calendar publication × allowance futures tenor × exchange quote timestamp and immutable timestamps.
2. `sources.py`: rights-aware loader of etsauction, etsreg official references and separately licensed feeds.
3. `baseline.py`: Calendar-month fixed seasonal allowance spread; must share opportunity universe and constraints with candidate.
4. `candidate.py`: Event study of auction schedule revisions and futures risk factors; add Partial equilibrium allowance banking model with endogenous industrial abatement and policy scenarios only after ablation warrants complexity.
5. `feasibility.py`: m,n are contract maturities; expectations only use public revisions available before trade, not full-year realized auction volumes.
6. `evaluation.py`: metrics EUA spread basis MAE, hedged risk reduction, net carry after fees, low-liquidity scenario loss, placebo, uncertainty and matched no-action baseline.
7. `report.py`: provenance and decision cost without asserting measured profitability.

## Identification challenges and alternatives
Policy revision expectations may be priced before official publication; futures/Registry coverage not contemporaneous. Use preregistered holdout splits, minimum economic materiality and delay-stressed baselines.
**Falsify:** No out-of-sample spread forecast or hedge benefit net of spreads after matched energy factors.

## Delivery and rollback
Synthetic deterministic tests → available-at real-data audit → walk-forward/paired counterfactual → read-only shadow mode → human approval. Disable candidate on missing rights/clock or limit violation and revert to baseline. No code exists yet.
