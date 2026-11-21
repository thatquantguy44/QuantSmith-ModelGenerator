# PLAN — European CSDR Penalty-Aware Settlement Queue Prioritization
**Architecture:** public/approved adapters → versioned temporal contract → eligibility gate → costed baseline → Constrained weighted-shortest-processing-time queue policy with eligibility rules → causal/economic replay → human review.

## Source ingestion and data shape
Public ESMA CSDR framework, synthetic ISIN liquidity/penalty groups, settlement instruction cutoff, fail reason and amendment history.
Event key: instruction × CSD × ISIN × intended settlement day × decision time. Record original filing/publication alongside first local actionable market clock. Penalty exclusions and rules must reflect versions legally in force before each instruction decision; ESMA technical advice is not automatically operative law.
Integrate publicly identified records only after separate terms-of-use and granularity checks. Private data stay in private approved runtime.

## Implementable modules (proposed)
1. `contracts.py`: pydantic models for instruction × CSD × ISIN × intended settlement day × decision time and immutable timestamps.
2. `sources.py`: rights-aware loader of esmacsdr, esmaexception official references and separately licensed feeds.
3. `baseline.py`: FIFO or largest-notional-first allowed settlement priority; must share opportunity universe and constraints with candidate.
4. `candidate.py`: Constrained weighted-shortest-processing-time queue policy with eligibility rules; add Approximate dynamic programming under stochastic matched delivery arrival times only after ablation warrants complexity.
5. `feasibility.py`: pi is processing sequence, i instruction, penalty_i applies only under effective CSDR exclusions and jurisdictional rules; capacity_t is eligible CSD processing capacity.
6. `evaluation.py`: metrics penalty liability, fail-days, priority-rule violations, operational throughput, placebo, uncertainty and matched no-action baseline.
7. `report.py`: provenance and decision cost without asserting measured profitability.

## Identification challenges and alternatives
Misclassification of non-attributable fail causes or legal exclusion yields incorrect optimized queues. Use preregistered holdout splits, minimum economic materiality and delay-stressed baselines.
**Falsify:** No statistically measurable improvement in held-out synthetic and later approved settlement scenarios under equal capacity.

## Delivery and rollback
Synthetic deterministic tests → available-at real-data audit → walk-forward/paired counterfactual → read-only shadow mode → human approval. Disable candidate on missing rights/clock or limit violation and revert to baseline. No code exists yet.
