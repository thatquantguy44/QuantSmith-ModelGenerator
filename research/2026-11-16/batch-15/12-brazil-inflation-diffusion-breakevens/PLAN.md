# Implementation plan — Brazil Inflation Diffusion versus Breakeven Carry

**Scope:** Brazil; local nominal and inflation-linked government bonds. No modules described here currently exist in this batch.

## Data contract and architecture

Propose `adapters/brazil_inflation_events.py` => immutable raw manifest => `point_in_time/asof.py` => `brazil_inflation_diffusion_breakevens/features.py` => `baseline.py` / `candidate.py` => `evaluation.py` => review artifact. Native grain is **inflation release x survey public version x matched bond pair**. Required domain fields: BCB public inflation/Focus releases, component-level official IPCA data to be resolved before implementation, dated expectations distributions, bond cash flows/indexation conventions, executable nominal and real curves and BRL hedge quotes.

The common event envelope is `(entity_id, source_id, source_version, observed_at, published_at, received_at, available_at, effective_at, unit, currency, rights_class, payload_hash)`. Historical receive times may be unknown: record assumed latency and its provenance separately, never present it as an observed receipt. As-of joins select the most recent version actually available at the decision instant, retaining prior versions and amendments.

## Domain transformation and decision clock

Build released inflation diffusion, survey dispersion and known indexation carry. Target: 63-session DV01-neutral excess breakeven return net of mechanical carry. Trade no earlier than next Sao Paulo session after verified inflation and survey publication, with one-hour processing lag. Survey collection dates are never treated as public timestamps. Keep pending announcements distinct from legally effective constraints. Do not train on a later correction, a future completion/outcome or a delisted-only survivor universe.

## Model alternatives

Start with Carry/roll plus headline inflation surprise using a fixed ridge regression and identical risk budget. Then implement Sparse distributed-lag regression with local-projection diagnostics. The expensive alternative is Bayesian inflation component state-space model with scenario-robust breakeven sizing; it is eligible only after a positive baseline-to-candidate comparison and a sufficient sample. Prefer the baseline if the advanced method's additional complexity does not clear net economic gates.

## Reviewable outputs and fallback

Return breakeven forecast, DV01 hedge and market-access gate. Save input manifest, time-mask violations, fit window, chosen parameters, cost scenario and reason for every excluded row. Unresolved official IPCA component source, tax convention or vintage timestamp blocks any empirical claim; all returns retain BRL and hedged-USD views. Exceptions return HOLD/BLOCKED and preserve the original decision/book. No adapter may send orders, change contractual prices or upload private records.

## Dependencies and boundaries

Licensed Brazilian nominal/real bond curves and constituent return/terms history; public BCB series are not executable curves. Optional authorized execution data; no domestic account or trading permission established. Public feasibility comes first; an absent private adapter is an explicit production blocker, not a justification to synthesize a historical result. Capacity review: Illustrative $40m duration-matched overlay; constrain pair DV01 and <=1% of observed issue turnover. Local liquidity, BRL hedging, indexation and applicable taxes must be priced before investment use. Shared libraries are specified in [TOOLING](TOOLING.md), tests in [EVALS](EVALS.md).
