# PLAN — SFTR Reporting Regime Drift and Public-Private Divergence Detector
**Architecture:** public/approved adapters → versioned temporal contract → eligibility gate → costed baseline → Robust multivariate Bayesian online change-point detection → causal/economic replay → human review.

## Source ingestion and data shape
ESMA reporting rules and publications, public aggregate exposures where available, historical methodology changes, synthetic backdated schema versions.
Event key: SFTR public aggregate series × jurisdiction × report vintage. Record original filing/publication alongside first local actionable market clock. Use publication timestamps and repository versions, not reporting reference dates; detailed transaction data are supervisor-restricted.
Integrate publicly identified records only after separate terms-of-use and granularity checks. Private data stay in private approved runtime.

## Implementable modules (proposed)
1. `contracts.py`: pydantic models for SFTR public aggregate series × jurisdiction × report vintage and immutable timestamps.
2. `sources.py`: rights-aware loader of esmasftr, esma2026 official references and separately licensed feeds.
3. `baseline.py`: Fixed ±3-sigma z-score alert on each series; must share opportunity universe and constraints with candidate.
4. `candidate.py`: Robust multivariate Bayesian online change-point detection; add Hierarchical regime/missingness change-point models with document version embeddings as covariates only after ablation warrants complexity.
5. `feasibility.py`: q is alarm threshold chosen before holdout; changes attributed to reporting are hypotheses until repository audit.
6. `evaluation.py`: metrics break detection delay, false alarms, post-correction economic interpretation stability, placebo, uncertainty and matched no-action baseline.
7. `report.py`: provenance and decision cost without asserting measured profitability.

## Identification challenges and alternatives
Only public aggregate data may be available, making root-cause verification incomplete. Use preregistered holdout splits, minimum economic materiality and delay-stressed baselines.
**Falsify:** Synthetic change fixtures not detected within agreed delay or false alerts exceed preregistered burden.

## Delivery and rollback
Synthetic deterministic tests → available-at real-data audit → walk-forward/paired counterfactual → read-only shadow mode → human approval. Disable candidate on missing rights/clock or limit violation and revert to baseline. No code exists yet.
