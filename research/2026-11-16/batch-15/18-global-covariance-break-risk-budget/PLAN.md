# Implementation plan — Global Covariance-Break Risk-Budget Controller

**Scope:** US, Europe, Japan and liquid EM; equity, rates, FX and commodities. No modules described here currently exist in this batch.

## Data contract and architecture

Propose `adapters/global_session_returns.py` => immutable raw manifest => `point_in_time/asof.py` => `global_covariance_break_risk_budget/features.py` => `baseline.py` / `candidate.py` => `evaluation.py` => review artifact. Native grain is **instrument x completed local session x common information cutoff**. Required domain fields: Daily index/futures/ETF total returns and FX, point-in-time instrument starts/ends, roll calendars, trading sessions, bid/ask and cost curves. H.15 can support rate diagnostics but is not a global total-return panel.

The common event envelope is `(entity_id, source_id, source_version, observed_at, published_at, received_at, available_at, effective_at, unit, currency, rights_class, payload_hash)`. Historical receive times may be unknown: record assumed latency and its provenance separately, never present it as an observed receipt. As-of joins select the most recent version actually available at the decision instant, retaining prior versions and amendments.

## Domain transformation and decision clock

Build lag-aware covariance, break statistic and marginal turnover cost. Target: realized risk-contribution tracking error at matched turnover and volatility. Decide at 16:30 America/New_York using only completed market sessions and public data received by then; execute each market's next liquid session. Stale Asian observations remain lagged rather than filled with later prices. Keep pending announcements distinct from legally effective constraints. Do not train on a later correction, a future completion/outcome or a delisted-only survivor universe.

## Model alternatives

Start with Monthly risk parity using 60-day EWMA covariance and fixed weight caps; compare a simple shrinkage covariance with no break detection. Then implement Sequential covariance change detector plus shrinkage and cost-aware no-trade bands. The expensive alternative is Distributionally robust risk-budget optimization over post-break covariance ambiguity sets; it is eligible only after a positive baseline-to-candidate comparison and a sufficient sample. Prefer the baseline if the advanced method's additional complexity does not clear net economic gates.

## Reviewable outputs and fallback

Return hold/rebalance research decision, risk-contribution certificate and stale-session report. Save input manifest, time-mask violations, fit window, chosen parameters, cost scenario and reason for every excluded row. All returns carry local session end and actual receive time; no forward fill across a market closure without a stale flag. Exceptions return HOLD/BLOCKED and preserve the original decision/book. No adapter may send orders, change contractual prices or upload private records.

## Dependencies and boundaries

Licensed global point-in-time index/futures/ETF total returns with delistings, rolls and executable cost history. Optional authorized portfolio limits and execution costs; synthetic constraints suffice for initial software. Public feasibility comes first; an absent private adapter is an explicit production blocker, not a justification to synthesize a historical result. Capacity review: Illustrative $100m liquid multi-asset allocation; cap <=1% ADV and add market-specific impact, rolls and FX conversion. Capacity derives from instrument liquidity, not covariance model size. Shared libraries are specified in [TOOLING](TOOLING.md), tests in [EVALS](EVALS.md).
