# PLAN — Japan FX Intervention Impact and Option-Skew Persistence
**Architecture:** public/approved adapters → versioned temporal contract → eligibility gate → costed baseline → Disclosure-timestamp event study with matched controls and local projections → causal/economic replay → human review.

## Source ingestion and data shape
MOF monthly/quarterly intervention releases and dates, spot FX, short-term rate differential, timestamped USDJPY options/forward data.
Event key: intervention disclosure event × FX option tenor × quote timestamp. Record original filing/publication alongside first local actionable market clock. MOF 2026 Q3 intervention details published Nov 9, 2026; never use ex-post intervention date labels in same-day live-time signals.
Integrate publicly identified records only after separate terms-of-use and granularity checks. Private data stay in private approved runtime.

## Implementable modules (proposed)
1. `contracts.py`: pydantic models for intervention disclosure event × FX option tenor × quote timestamp and immutable timestamps.
2. `sources.py`: rights-aware loader of mofq3, mofmonthly official references and separately licensed feeds.
3. `baseline.py`: Standard spot momentum and monetary-policy announcement dummy; must share opportunity universe and constraints with candidate.
4. `candidate.py`: Disclosure-timestamp event study with matched controls and local projections; add Partial-identification causal synthetic control separating information, execution and portfolio-flow channels only after ablation warrants complexity.
5. `feasibility.py`: InterventionKnownAt_t is zero until event is publicly known or release issued; h is forward horizon, and skew is an executable options quote measure.
6. `evaluation.py`: metrics incremental forward skew/vol forecast skill, delta-hedged net P&L, placebo events, risk-adjusted drawdown, placebo, uncertainty and matched no-action baseline.
7. `report.py`: provenance and decision cost without asserting measured profitability.

## Identification challenges and alternatives
Actual intervention execution is not transparently known in real time; small event count undermines causal certainty. Use preregistered holdout splits, minimum economic materiality and delay-stressed baselines.
**Falsify:** No differential response versus rate/central-bank news controls on withheld intervention disclosures or net-option-cost results.

## Delivery and rollback
Synthetic deterministic tests → available-at real-data audit → walk-forward/paired counterfactual → read-only shadow mode → human approval. Disable candidate on missing rights/clock or limit violation and revert to baseline. No code exists yet.
