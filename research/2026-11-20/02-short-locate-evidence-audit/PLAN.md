# PLAN — Reg SHO Locate Evidence and Borrow-Capacity Audit Engine
**Architecture:** public/approved adapters → versioned temporal contract → eligibility gate → costed baseline → Typed event-sourcing finite-state verification with causal explainability → causal/economic replay → human review.

## Source ingestion and data shape
Synthetic short-sale order events, documented locate timestamps, source identity, shares remaining, exemptions and post-trade recalls; later private desk records only if approved.
Event key: short-sale request × account × security × source × event timestamp. Record original filing/publication alongside first local actionable market clock. Locate documentation and quantity must be timestamped before short sale; revised records cannot retroactively authorize prior orders.
Integrate publicly identified records only after separate terms-of-use and granularity checks. Private data stay in private approved runtime.

## Implementable modules (proposed)
1. `contracts.py`: pydantic models for short-sale request × account × security × source × event timestamp and immutable timestamps.
2. `sources.py`: rights-aware loader of secsho official references and separately licensed feeds.
3. `baseline.py`: End-of-day deterministic locate exception SQL rules; must share opportunity universe and constraints with candidate.
4. `candidate.py`: Typed event-sourcing finite-state verification with causal explainability; add Conformal anomaly scoring for ambiguous evidence routed to human review, never autonomous compliance override only after ablation warrants complexity.
5. `feasibility.py`: FN is an incorrectly accepted exception, FP an incorrectly blocked valid locate, and Delay is processing latency; all compliance rules require human-verified effective policy and exemptions.
6. `evaluation.py`: metrics prevented invalid requests, false blocks, recall error, audit completion time, p99 latency, placebo, uncertainty and matched no-action baseline.
7. `report.py`: provenance and decision cost without asserting measured profitability.

## Identification challenges and alternatives
Reg SHO exemptions, broker responsibilities and settlement rules require qualified legal interpretation. Use preregistered holdout splits, minimum economic materiality and delay-stressed baselines.
**Falsify:** Fails to flag intentionally missing/expired/overused locates on synthetic fixtures or blocks materially more valid trades than comparator.

## Delivery and rollback
Synthetic deterministic tests → available-at real-data audit → walk-forward/paired counterfactual → read-only shadow mode → human approval. Disable candidate on missing rights/clock or limit violation and revert to baseline. No code exists yet.
