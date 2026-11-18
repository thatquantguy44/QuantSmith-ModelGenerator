# Evaluation contract — Repo Compression with Cash-Flow Preservation

**Empirical results: none. All experiment execution is BLOCKED.**

## Primary comparison and falsification

Target: retained gross notional and verified per-date cash/security conservation. Baseline: Cancel exact opposite tickets bilaterally within a legal set; otherwise hold the original book. Candidate: Mixed-integer minimum-cost circulation with exact cash-flow conservation. Optional advanced model: Robust multi-period compression with consent uncertainty and settlement-feasibility cuts. Metrics: gross reduction, message reduction, all-in cost, maximum flow residual, consent acceptance and solve time. Freeze one primary economic gate and report secondary diagnostics without selectively promoting their successes.

**Objective stop/go:** GO only with >=15% gross reduction and >=10% realized operational cost reduction on held-out eligible sets; every cash/security residual <=$0.01 cash or zero security units; zero consent violations. STOP on any economic transfer or if gains vanish after legal filtering.

## Point-in-time and survival controls

Freeze the ledger at 14:00 America/New_York; use only confirmed records ingested by 13:55 and decisions before the relevant service cutoff. Cash-flow amendments received later enter the next solve. Test observed/published/received/available/effective timestamps independently. Append revisions; never latest-vintage overwrite. Historical ingest latency is an assumption unless recorded. Training-only normalization, feature selection, calibration and parameter selection are mandatory. Keep failed outcomes, terminated contracts, exited instruments and incomplete cohorts with declared censoring; compare the historical eligible universe, not current survivors.

Split chronologically with an embargo at least as long as the maximum target/exposure overlap. Keep issuer/event/season groups together. Require adequate independent clusters before confidence intervals; rows are not independent replications. Log all attempted variants and adjust for selection across the 20-idea research family; holdout failure remains failure.

## Negative tests and operational stress

- Domain fixture: Construct a three-node cycle with mismatched maturity dates: it must remain uncompressed; changing one consent flag must remove every affected action.
- Future version inserted one second after decision: excluded; missing timestamp/rights: BLOCKED; duplicate payload hash: deduplicated; currency/unit mismatch: rejected.
- Destroy target information with in-group permutation: economic advantage should disappear within declared uncertainty. A solver feasibility test need not disappear, but may not imply alpha.
- Replay source outage, time-zone/DST mismatch, absent instrument and stale quote with explicit HOLD/BLOCKED. Never silently zero-fill unavailable data.
- Double spreads/impact and halve eligible capacity. Illustrative $1bn eligible matched book; no directional risk capital assumed. Economics come from fewer messages and approved gross-capacity charges, not treating all removed notional as regulatory capital relief. Report gross versus net benefits and explain any transition from positive to negative.

## Shadow and production criteria

At least 60 eligible decisions and 90 calendar days, extending through a complete native seasonal/event cycle, with zero hard-constraint/time violations; all overrides and fallback decisions reviewed. Require the primary threshold above plus measured net costs and a verified operational owner. For a proposed 5,000-ticket set, target p95 solve time <=60 seconds and exact conservation certificate; infeasible or timed-out solves return original book. Any unknown legal right or inaccessible input halts promotion. There is no automatic deployment.

## Evidence required in a later results artifact

Code commit, dependency lock hash, immutable source/version manifest, exact split definitions, effective cluster count, baseline/candidate outputs, confidence bounds, cost/capacity scenarios, every negative-test result, rejected rows and signed review state. Academic interest: Medium: constrained compression with dated multi-asset conservation; novelty relative to existing compression literature needs a dedicated review. A theory link or passing synthetic test is not evidence of the hypothesis.
