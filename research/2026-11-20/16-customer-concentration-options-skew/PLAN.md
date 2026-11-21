# PLAN — Issuer Customer-Concentration Disclosure to Earnings Options Skew
**Architecture:** public/approved adapters → versioned temporal contract → eligibility gate → costed baseline → Censored-disclosure panel with inverse observation probability adjustment → causal/economic replay → human review.

## Source ingestion and data shape
SEC EDGAR original issuer filings, customer concentration disclosures, single-stock option surface, earnings calendar, liquidity and corporate actions.
Event key: issuer accepted filing × reported customer share × options quote timestamp. Record original filing/publication alongside first local actionable market clock. Use SEC acceptance timestamps and first published disclosure, not retroactive tagged XBRL after amended filings.
Integrate publicly identified records only after separate terms-of-use and granularity checks. Private data stay in private approved runtime.

## Implementable modules (proposed)
1. `contracts.py`: pydantic models for issuer accepted filing × reported customer share × options quote timestamp and immutable timestamps.
2. `sources.py`: rights-aware loader of secapi, secfiling official references and separately licensed feeds.
3. `baseline.py`: Size/leverage/industry/earnings event-only option skew estimator; must share opportunity universe and constraints with candidate.
4. `candidate.py`: Censored-disclosure panel with inverse observation probability adjustment; add Jump-diffusion structural model of concentrated-customer exit hazard only after ablation warrants complexity.
5. `feasibility.py`: HHI is sum of squared disclosed customer revenue shares (bounded/partially observed); t-known is filing dissemination time, not fiscal year end.
6. `evaluation.py`: metrics post-filing skew residual, risk hedge efficiency, delta-neutral net performance and disclosure coverage, placebo, uncertainty and matched no-action baseline.
7. `report.py`: provenance and decision cost without asserting measured profitability.

## Identification challenges and alternatives
Customer concentrations may be anonymized and nonrandomly omitted; options trade data can be illiquid. Use preregistered holdout splits, minimum economic materiality and delay-stressed baselines.
**Falsify:** No post-filing incremental skew or hedge gain beyond conventional earnings-related jump risk.

## Delivery and rollback
Synthetic deterministic tests → available-at real-data audit → walk-forward/paired counterfactual → read-only shadow mode → human approval. Disable candidate on missing rights/clock or limit violation and revert to baseline. No code exists yet.
