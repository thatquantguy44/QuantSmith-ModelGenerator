# Implementation plan — US CMBS Refinance Hazard from Public Disclosures

**Scope:** United States commercial property and securitized credit. No modules described here currently exist in this batch.

## Data contract and architecture

Propose `adapters/cmbs_public_vintages.py` => immutable raw manifest => `point_in_time/asof.py` => `us_cmbs_refinance_disclosure_hazard/features.py` => `baseline.py` / `candidate.py` => `evaluation.py` => review artifact. Native grain is **loan x public reporting vintage x maturity/outcome event**. Required domain fields: Public ABS-EE/10-D/10-K filings, accepted timestamps, loan maturity/amendment histories, NOI/DSCR field definitions, property type, rate terms and outcome reports; licensed bond/REIT pricing and servicing histories as needed. An example filing does not establish complete coverage.

The common event envelope is `(entity_id, source_id, source_version, observed_at, published_at, received_at, available_at, effective_at, unit, currency, rights_class, payload_hash)`. Historical receive times may be unknown: record assumed latency and its provenance separately, never present it as an observed receipt. As-of joins select the most recent version actually available at the decision instant, retaining prior versions and amendments.

## Domain transformation and decision clock

Build public refinance cash gap, maturity hazard and amendment lineage. Target: 12-month competing refinance outcomes and portfolio loss at fixed spread carry. Update risk after SEC acceptance plus one business day parsing/review; a prior reporting month's NOI remains unavailable until filing. Amendments are appended and never rewrite earlier risk snapshots. Keep pending announcements distinct from legally effective constraints. Do not train on a later correction, a future completion/outcome or a delisted-only survivor universe.

## Model alternatives

Start with Logistic distress model using months-to-maturity and last publicly available DSCR with fixed rate-shock scenarios. Then implement Competing-risk survival model with refinance cash-gap covariates. The expensive alternative is Hierarchical property-cycle hazard and cash-flow waterfall scenario optimization; it is eligible only after a positive baseline-to-candidate comparison and a sufficient sample. Prefer the baseline if the advanced method's additional complexity does not clear net economic gates.

## Reviewable outputs and fallback

Return competing-outcome probabilities, missing-field coverage and tranche mapping limits. Save input manifest, time-mask violations, fit window, chosen parameters, cost scenario and reason for every excluded row. Require filing accession and field-level source path; unparsed or contradictory outcome definitions fail closed for that loan. Exceptions return HOLD/BLOCKED and preserve the original decision/book. No adapter may send orders, change contractual prices or upload private records.

## Dependencies and boundaries

Licensed servicing, CMBS waterfall and executable bond-price history; public filings may not cover all required terms. Optional authorized portfolio constraints; no borrower documents or nonpublic property records obtained. Public feasibility comes first; an absent private adapter is an explicit production blocker, not a justification to synthesize a historical result. Capacity review: Illustrative $50m credit exposure; position limits depend on tranche liquidity and loss subordination. No assumption that a loan risk score is directly tradable or every CMBS has a liquid hedge. Shared libraries are specified in [TOOLING](TOOLING.md), tests in [EVALS](EVALS.md).
