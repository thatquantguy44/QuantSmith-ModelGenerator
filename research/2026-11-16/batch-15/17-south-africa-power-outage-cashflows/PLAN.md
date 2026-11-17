# Implementation plan — South African Power Reliability Equity Exposure

**Scope:** South Africa; JSE industrials, retailers and exporters. No modules described here currently exist in this batch.

## Data contract and architecture

Propose `adapters/south_africa_power.py` => immutable raw manifest => `point_in_time/asof.py` => `south_africa_power_outage_cashflows/features.py` => `baseline.py` / `candidate.py` => `evaluation.py` => review artifact. Native grain is **firm x day and dated generation/outage release**. Required domain fields: Eskom public system/outage releases, exact publication versions, issuer public energy/backup disclosures, geography, sector, JSE returns including delistings, ZAR and commodity controls. Historical spatial outage maps are an unresolved source gate.

The common event envelope is `(entity_id, source_id, source_version, observed_at, published_at, received_at, available_at, effective_at, unit, currency, rights_class, payload_hash)`. Historical receive times may be unknown: record assumed latency and its provenance separately, never present it as an observed receipt. As-of joins select the most recent version actually available at the decision instant, retaining prior versions and amendments.

## Domain transformation and decision clock

Build pre-disclosed energy intensity, backup coverage and released outage innovation. Target: power-shock residual equity sensitivity and hedge downside error. Update after verified Eskom publication; act next JSE session with prior-disclosed firm exposures. Never label realized electricity usage as known before earnings disclosure. Keep pending announcements distinct from legally effective constraints. Do not train on a later correction, a future completion/outcome or a delisted-only survivor universe.

## Model alternatives

Start with National load-shedding stage interacted with fixed sector averages and a market/FX hedge. Then implement Panel fixed effects with pre-period exposure interactions and event-placebo tests. The expensive alternative is Hierarchical causal sensitivity bounds plus constrained cash-flow hedge portfolio; it is eligible only after a positive baseline-to-candidate comparison and a sufficient sample. Prefer the baseline if the advanced method's additional complexity does not clear net economic gates.

## Reviewable outputs and fallback

Return firm sensitivity bounds and neutral power-risk hedge research basket. Save input manifest, time-mask violations, fit window, chosen parameters, cost scenario and reason for every excluded row. Any exposure inferred from a later filing is unavailable for earlier dates; preserve source language and disclosure spans. Exceptions return HOLD/BLOCKED and preserve the original decision/book. No adapter may send orders, change contractual prices or upload private records.

## Dependencies and boundaries

Licensed JSE total-return/delisting history, firm reference mapping and intraday prices if needed. Optional public-company-approved operating exposure detail; never required or obtained for this public proposal. Public feasibility comes first; an absent private adapter is an explicit production blocker, not a justification to synthesize a historical result. Capacity review: Illustrative $20m hedge sleeve capped at 1% ADV with local spreads, market access and ZAR hedge costs; concentrated names can exhaust capacity rapidly. Shared libraries are specified in [TOOLING](TOOLING.md), tests in [EVALS](EVALS.md).
