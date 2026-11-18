# Implementation plan — Sterling ILTR Auction Demand Smoothing

**Scope:** United Kingdom; GBP central-bank secured liquidity. No modules described here currently exist in this batch.

## Data contract and architecture

Propose `adapters/boe_iltr.py` => immutable raw manifest => `point_in_time/asof.py` => `sterling_iltr_maturity_ladder/features.py` => `baseline.py` / `candidate.py` => `evaluation.py` => review artifact. Native grain is **auction x collateral set x release version**. Required domain fields: Published BoE operation results, facility rules, publication timestamps, collateral-set spreads and tenors; simulated reserve paths; licensed GBP alternative-funding quotes for later testing.

The common event envelope is `(entity_id, source_id, source_version, observed_at, published_at, received_at, available_at, effective_at, unit, currency, rights_class, payload_hash)`. Historical receive times may be unknown: record assumed latency and its provenance separately, never present it as an observed receipt. As-of joins select the most recent version actually available at the decision instant, retaining prior versions and amendments.

## Domain transformation and decision clock

Build clearing-spread intervals, reserve coverage and maturity bucket exposure. Target: cost of a reserve maturity ladder subject to stressed coverage. Use results only after public release; plan by 09:00 Europe/London before an operation using earlier operations and latest approved reserve forecast. Verify each current auction deadline before a live pilot. Keep pending announcements distinct from legally effective constraints. Do not train on a later correction, a future completion/outcome or a delisted-only survivor universe.

## Model alternatives

Start with Equal weekly maturities with bids at independently approved maximum willingness-to-pay; compare a single-auction funding plan separately. Then implement Shape-constrained aggregate supply-curve estimation plus stochastic ladder optimization. The expensive alternative is Partially identified robust auction planning over a set of rival-demand curves; it is eligible only after a positive baseline-to-candidate comparison and a sufficient sample. Prefer the baseline if the advanced method's additional complexity does not clear net economic gates.

## Reviewable outputs and fallback

Return auction cash-demand ladder with allocation sensitivity bounds. Save input manifest, time-mask violations, fit window, chosen parameters, cost scenario and reason for every excluded row. Every schedule uses Europe/London DST and verified effective facility calibration; missing auction rule version blocks recommendation. Exceptions return HOLD/BLOCKED and preserve the original decision/book. No adapter may send orders, change contractual prices or upload private records.

## Dependencies and boundaries

Licensed SONIA/GBP funding curves and bond prices; public auction results alone do not establish executable savings. Permissioned reserve forecasts, approved bid limits and collateral access; absent. Public feasibility comes first; an absent private adapter is an explicit production blocker, not a justification to synthesize a historical result. Capacity review: Illustrative GBP500m reserve need in USD-equivalent ROI; size must be small relative to auction capacity or explicitly model own impact. Operational access, collateral prepositioning and bridge-funding limits bind. Shared libraries are specified in [TOOLING](TOOLING.md), tests in [EVALS](EVALS.md).
