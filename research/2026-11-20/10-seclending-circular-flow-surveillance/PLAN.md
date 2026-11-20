# PLAN — Securities-Lending Circular Flow Surveillance via Temporal Graphs
**Architecture:** public/approved adapters → versioned temporal contract → eligibility gate → costed baseline → Temporal graph motif detection with exact deterministic event identity → causal/economic replay → human review.

## Source ingestion and data shape
Synthetic multi-party loan/return event graph, matched collateral movement, legitimate transfer controls, anonymized case annotations if permitted.
Event key: synthetic securities loan transfer edge × security × event timestamp. Record original filing/publication alongside first local actionable market clock. Create graph only from recorded transfers visible before alert time; disallow knowledge of subsequent investigation outcomes in features.
Integrate publicly identified records only after separate terms-of-use and granularity checks. Private data stay in private approved runtime.

## Implementable modules (proposed)
1. `contracts.py`: pydantic models for synthetic securities loan transfer edge × security × event timestamp and immutable timestamps.
2. `sources.py`: rights-aware loader of esmasftr, secsho official references and separately licensed feeds.
3. `baseline.py`: Two-party net-quantity turnaround rules; must share opportunity universe and constraints with candidate.
4. `candidate.py`: Temporal graph motif detection with exact deterministic event identity; add Weakly supervised dynamic graph anomaly ranking with human-in-loop conformal calibration only after ablation warrants complexity.
5. `feasibility.py`: K is review budget; temporal motif score must be conditioned on legitimate inventory transfers and settlement cycles.
6. `evaluation.py`: metrics precision at K, seeded motif recall, legitimate-flow false-alerts, explanation fidelity, placebo, uncertainty and matched no-action baseline.
7. `report.py`: provenance and decision cost without asserting measured profitability.

## Identification challenges and alternatives
False accusations, privileged customer data, and severe sample-selection bias in investigated cases. Use preregistered holdout splits, minimum economic materiality and delay-stressed baselines.
**Falsify:** No precision@K gain against pairwise rules under benign high-volume churn fixtures.

## Delivery and rollback
Synthetic deterministic tests → available-at real-data audit → walk-forward/paired counterfactual → read-only shadow mode → human approval. Disable candidate on missing rights/clock or limit violation and revert to baseline. No code exists yet.
