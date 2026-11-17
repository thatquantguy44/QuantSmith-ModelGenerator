# Implementation plan — US–Europe Corridor Variance and Jump-Risk Budget

**Scope:** US S&P 500 and euro-area equity index options. No modules described here currently exist in this batch.

## Data contract and architecture

Propose `adapters/global_option_chains.py` => immutable raw manifest => `point_in_time/asof.py` => `global_volatility_corridor_jump_budget/features.py` => `baseline.py` / `candidate.py` => `evaluation.py` => review artifact. Native grain is **market x option expiry/strike x quote instant plus intraday underlying bars**. Required domain fields: Public index methodology for background, synchronized bid/ask option chains, index/futures returns, expiries, dividends, rates and settlement rules. Intraday sampling and overnight jump handling are fixed before testing.

The common event envelope is `(entity_id, source_id, source_version, observed_at, published_at, received_at, available_at, effective_at, unit, currency, rights_class, payload_hash)`. Historical receive times may be unknown: record assumed latency and its provenance separately, never present it as an observed receipt. As-of joins select the most recent version actually available at the decision instant, retaining prior versions and amendments.

## Domain transformation and decision clock

Build corridor variance, overnight jump proxies, executable strip costs and tail hedge Greeks. Target: net option-strip carry and stress/tail loss at fixed hedge premium. Allocate at a common UTC snapshot when both markets have liquid executable quotes; use prior completed return bars only. Do not pair a European close with later US data as contemporaneous. Keep pending announcements distinct from legally effective constraints. Do not train on a later correction, a future completion/outcome or a delisted-only survivor universe.

## Model alternatives

Start with Equal-vega option-strip variance exposure by market with a fixed put-spread tail hedge and identical costs. Then implement Semiparametric continuous/jump decomposition and constrained risk-budget allocation. The expensive alternative is Distributionally robust jump-diffusion option-portfolio optimization; it is eligible only after a positive baseline-to-candidate comparison and a sufficient sample. Prefer the baseline if the advanced method's additional complexity does not clear net economic gates.

## Reviewable outputs and fallback

Return vega allocation, explicit option-strip positions and stress funding requirements. Save input manifest, time-mask violations, fit window, chosen parameters, cost scenario and reason for every excluded row. Reject crossed/stale quotes and impossible option monotonicity; no interpolation may create executable liquidity that was not quoted. Exceptions return HOLD/BLOCKED and preserve the original decision/book. No adapter may send orders, change contractual prices or upload private records.

## Dependencies and boundaries

Licensed US/European options, intraday underlying data and exchange settlement/transaction rights; none acquired. Optional approved margin and execution accounts; no trading authority. Public feasibility comes first; an absent private adapter is an explicit production blocker, not a justification to synthesize a historical result. Capacity review: Illustrative $20m capital budget with explicit vega/margin limits, <=1% option-strike volume/open-interest bounds and no unlimited tail-risk assumption. Capacity likely concentrated in a few liquid expiries. Shared libraries are specified in [TOOLING](TOOLING.md), tests in [EVALS](EVALS.md).
