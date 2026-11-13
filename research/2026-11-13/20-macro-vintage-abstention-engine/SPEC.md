# SPEC — Macro-Vintage Integrity Engine with Prediction Abstention
**ID:** QMG-20261113-20 · **Status:** Draft; human approval required · **Category:** B · Domestic & global markets · **Geography:** United States, euro area and OECD countries

## Problem and decision
Most macro backtests silently use revised values and revised seasonal adjustments; an ML model may score highly on information that did not exist at decision time.
**Decision supported:** Permit or abstain from a macro risk-signal update based on measured vintage quality, published delays and expected decision value.

## H1 versus H0
**H1:** A vintage-aware abstention gate reduces false active signals and revisional backtest overstatement versus always-on macro factor models.
**H0:** A cost-inclusive Always-on macro momentum score built from latest-vintage series. matches or exceeds the candidate on strictly out-of-sample decisions. The intent is falsification, not confirmation.

## Mathematical problem and domain
```text
Trade_t=1{E[utility(signal_t)|vintage_quality_t] > cost_t and quality_t>=q_min}; otherwise hold benchmark
```
quality measures source reliability, revision uncertainty, coverage and release history; expected utility estimated strictly from past vintages.
**Capacity and eligibility:** Primarily a reusable research data-quality service; alpha/executable returns need licensed market backtest.
Unspecified coefficients must be estimated only from training windows and no undocumented constraint may be relaxed.

## Source, clock and data contract
ALFRED historical revisions, ECB yield releases, OECD SDMX data vintage calendars, US/global market proxies. **Observation grain:** economic indicator × observation period × release date × vintage ID. **Decision horizon:** update only after first verified public release; revisions must enter as new events, not retroactively.
At minimum require `observation_id`, `effective_at`, `published_at`, `available_at`, `ingested_at`, `source_uri`, `license_class`, `revision_id`, `unit`. `available_at <= decision_time` is mandatory for all market signals. New revisions create new records and must not silently overwrite historical decisions.

## Functional and nonfunctional requirements
| ID | Explicit requirement | Priority |
|---|---|---|
| REQ-001 | Model the permitted choice: Permit or abstain from a macro risk-signal update based on measured vintage quality, published delays and expected decision value. | Must |
| REQ-002 | Reproduce feasible benchmark: Always-on macro momentum score built from latest-vintage series. | Must |
| REQ-003 | Implement candidate As-of macro feature store with release-confidence model and abstention. only after benchmark | Must |
| REQ-004 | Report revision-induced backtest bias, selective risk loss, coverage, false alarm rate, time-to-data-availability. and matched capacity/execution economics | Must |
| NFR-001 | Deterministic fixture replay, point-in-time lineage and seed/config pinning | Must |
| NFR-002 | Confidentiality, access/market eligibility, source licensing and manual review | Must |

## Acceptance criteria
| ID | Covers | Testable requirement |
|---|---|---|
| AC-001 | REQ-001,NFR-001 | Reject unavailable source vintages and impossible decision clocks |
| AC-002 | REQ-002 | Synthetic benchmark passes unit, cost and eligibility invariants |
| AC-003 | REQ-003 | Candidate uses same opportunities/cost rules; reproducible paired holdout |
| AC-004 | REQ-004 | Net economic metrics, intervals, sensitivity and capacity displayed |
| AC-005 | NFR-002 | Public output blocks private rows and unresolved authorization |

## Research economics
USD $130k hypothetical 24-month engineering/data/maintenance cost; gross benefit sensitivity $20k–$245k over 24 months. Net ROI = (gross benefit − cost)/cost = **-85% to 88%**. NOT forecast or historical measurement. Economic lever: scenario: reduce failed model deployment and wasted model-validation hours, plus any trading uplift; 24-month benefits unmeasured.. Source availability: FRED real-time API explicitly supports known-as-of periods; series availability and revision dates require series-specific verification.
Funding, transaction cost and execution constraints require separate real calibration.

## Primary risks and negative gates
- **RISK-001:** ALFRED historical series coverage, future revisions and OECD methodological breaks can be incomplete; abstention selection bias.
- **RISK-002:** Data sparsity, nonstationarity, multiple testing and selection effects.
- **RISK-003:** Rights, settlement or investability restrictions may make an apparent opportunity infeasible.
- **Predeclared stop:** Reject if abstention fails to reduce loss on corrected vintage history or simply abstains from all market decisions.
- **Non-goals:** Trading, legal/compliance approvals, publishing real P&L, or deployment from this spec alone.
