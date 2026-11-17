# Evaluation contract — US CMBS Refinance Hazard from Public Disclosures

**Empirical results: none. All experiment execution is BLOCKED.**

## Primary comparison and falsification

Target: 12-month competing refinance outcomes and portfolio loss at fixed spread carry. Baseline: Logistic distress model using months-to-maturity and last publicly available DSCR with fixed rate-shock scenarios. Candidate: Competing-risk survival model with refinance cash-gap covariates. Optional advanced model: Hierarchical property-cycle hazard and cash-flow waterfall scenario optimization. Metrics: Brier/calibration, distress precision-recall, vintage drift, stress loss, carry retained and concentration. Freeze one primary economic gate and report secondary diagnostics without selectively promoting their successes.

**Objective stop/go:** GO if Brier improves >=10% and stress loss falls >=5% at same carry over a held-out issuance vintage; STOP if modification histories, exited loans or outcome timing are missing for >10% of sample.

## Point-in-time and survival controls

Update risk after SEC acceptance plus one business day parsing/review; a prior reporting month's NOI remains unavailable until filing. Amendments are appended and never rewrite earlier risk snapshots. Test observed/published/received/available/effective timestamps independently. Append revisions; never latest-vintage overwrite. Historical ingest latency is an assumption unless recorded. Training-only normalization, feature selection, calibration and parameter selection are mandatory. Keep failed outcomes, terminated contracts, exited instruments and incomplete cohorts with declared censoring; compare the historical eligible universe, not current survivors.

Split chronologically with an embargo at least as long as the maximum target/exposure overlap. Keep issuer/event/season groups together. Require adequate independent clusters before confidence intervals; rows are not independent replications. Log all attempted variants and adjust for selection across the 20-idea research family; holdout failure remains failure.

## Negative tests and operational stress

- Domain fixture: Replace an original loan maturity with a later extension and verify earlier features remain unchanged; include liquidated loans and enforce waterfall conservation under default scenarios.
- Future version inserted one second after decision: excluded; missing timestamp/rights: BLOCKED; duplicate payload hash: deduplicated; currency/unit mismatch: rejected.
- Destroy target information with in-group permutation: economic advantage should disappear within declared uncertainty. A solver feasibility test need not disappear, but may not imply alpha.
- Replay source outage, time-zone/DST mismatch, absent instrument and stale quote with explicit HOLD/BLOCKED. Never silently zero-fill unavailable data.
- Double spreads/impact and halve eligible capacity. Illustrative $50m credit exposure; position limits depend on tranche liquidity and loss subordination. No assumption that a loan risk score is directly tradable or every CMBS has a liquid hedge. Report gross versus net benefits and explain any transition from positive to negative.

## Shadow and production criteria

At least 60 eligible decisions and 90 calendar days, extending through a complete native seasonal/event cycle, with zero hard-constraint/time violations; all overrides and fallback decisions reviewed. Require the primary threshold above plus measured net costs and a verified operational owner. Require filing accession and field-level source path; unparsed or contradictory outcome definitions fail closed for that loan. Any unknown legal right or inaccessible input halts promotion. There is no automatic deployment.

## Evidence required in a later results artifact

Code commit, dependency lock hash, immutable source/version manifest, exact split definitions, effective cluster count, baseline/candidate outputs, confidence bounds, cost/capacity scenarios, every negative-test result, rejected rows and signed review state. Academic interest: High: public disclosure vintages and competing refinancing paths; publication depends on reliable field extraction and sample representativeness. A theory link or passing synthetic test is not evidence of the hypothesis.
