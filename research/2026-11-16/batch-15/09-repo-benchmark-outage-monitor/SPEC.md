# Specification — Repo Benchmark Outage and Revision Risk Monitor

**QMG-20261116-09 · A — Securities finance · research design, empirical state BLOCKED.**

## Decision and hypothesis

Choose whether a funding-risk report may use a published rate, show an uncertainty interval, or require manual review; never replace a contractual fallback. A publication-state monitor lowers material funding-risk reporting errors by at least 50% versus blindly carrying the last rate, with false escalation on fewer than 2% of ordinary releases.

```text
action_t=argmin_(a in {accept,interval,review}) E[L(a,r_true)|I_t] + review_cost(a); interval=[r_hat-z*sigma,r_hat+z*sigma], coverage>=0.99; contractual_rate=official_contract_rule
```

r_true is final same-day reference rate used solely as later evaluation label; I_t contains previously published rates, release state and notes; r_hat monitoring estimate; sigma forecast uncertainty; z calibrated using training-only residuals. L dollar reporting loss uses fixed rate-sensitive exposure and time fraction.

## Traceable requirements

| ID | Requirement | Objective acceptance |
|---|---|---|
| QMG-20261116-09-REQ-01 | Ingest reference rate x publication event x revision version | Source/version/hash, rights and all time fields present; reject invalid units. |
| QMG-20261116-09-REQ-02 | Build rate release age, version chain, contingency flag and interval width | Every constituent available_at <= decision_at; no revised-history overwrite. |
| QMG-20261116-09-REQ-03 | Implement baseline: Carry the most recent official rate and mark missing releases only after end of day. | Independent deterministic fixture and parity in risk/cost/information. |
| QMG-20261116-09-REQ-04 | Fit/solve Versioned publication-state rules plus robust short-horizon rate interval | Output hard-constraint certificate and holdout-ready predictions/actions. |
| QMG-20261116-09-REQ-05 | Evaluate reporting error and escalation burden under delayed/corrected publication | Apply the fixed primary gate below without post-hoc threshold changes. |
| QMG-20261116-09-REQ-06 | Produce accept/interval/review status, immutable as-of report and official-source pointer | Include uncertainty, rejected decisions, cost/capacity and source lineage. |

| ID | Nonfunctional/acceptance requirement |
|---|---|
| QMG-20261116-09-NFR-01 | Append-only publication ledger; fail closed on missing source/version and keep synthetic monitoring estimates in a separate schema. |
| QMG-20261116-09-NFR-02 | Deterministic seeds, immutable inputs, exact dependency hashes and no network in replay; private adapters disabled by default. |
| QMG-20261116-09-AC-01 | GO if >=50% reduction in material (>2 bp monitoring error) incidents and <2% false escalation over >=250 releases plus synthetic outages; interval coverage >=99%. STOP if rare-event evidence cannot separate improvement from excessive review. |
| QMG-20261116-09-AC-02 | Hide a morning release and reveal a later correction: morning output must stay immutable and explicitly uncertain; no synthetic estimate may populate a contractual-rate field. |
| QMG-20261116-09-AC-03 | Zero future-input assertions violated; all universe exits retained or explicitly explained; unmatched rights/timestamp rows excluded. |

## Data, economic units and failure semantics

Official rate releases, first-observed timestamps, revision footnotes, contingency notices, rates and ranges; OFR lagged aggregates may inform monitoring but are not contract benchmark substitutes. Clock: Snapshot at 08:15 America/New_York and again after verified revisions; only information received by each timestamp is usable. A 14:30 revision must not overwrite the morning feature snapshot. Distinguish event observation, public dissemination, local receipt and future effective date. Validate native amount, annualized rate, day-count and local currency before USD-equivalent ROI conversion. Missing data do not become zeros; unavailable actions return HOLD/BLOCKED with a reason.

## Risks and economics

Contingency/revision events are rare; injected outages are software stress tests, not evidence of historical economic benefit. OFR mean rates and official medians differ in coverage. Illustrative $1bn rate-sensitive monitored exposure; no trading position. Economic value is analyst time and correction effort; excluded speculative avoided trading losses. See [README](README.md) for full illustrative ROI arithmetic and [SOURCES](SOURCES.md) for verified link scope. Publication: Medium: benchmark-data resilience and reproducible counterfactual outages; rare events limit generalization.
