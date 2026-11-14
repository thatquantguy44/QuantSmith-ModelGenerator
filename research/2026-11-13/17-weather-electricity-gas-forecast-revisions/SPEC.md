# SPEC — Weather Forecast Revision as an Electricity-to-Gas Risk Hedge
**ID:** QMG-20261113-17 · **Status:** Draft; human approval required · **Category:** B · Domestic & global markets · **Geography:** US regional power markets and Henry Hub-linked energy

## Problem and decision
Weather surprises drive power demand, but using finalized observed weather in a historical strategy produces impossible lead-time and exaggerates energy trading edge.
**Decision supported:** Size gas/power-linked hedges using only prior-issued weather forecasts and expected net-load revisions.

## H1 versus H0
**H1:** Timestamped forecast *revisions* explain next-session electricity net-load stress better than absolute forecast temperature or seasonal normals.
**H0:** A cost-inclusive Seasonal degree-day demand regression and absolute temperature forecasts. matches or exceeds the candidate on strictly out-of-sample decisions. The intent is falsification, not confirmation.

## Mathematical problem and domain
```text
Revision_r,t = LoadForecast_r,t^(latest issued) - LoadForecast_r,t^(prior issued); Hedge_t=clip(β*Revision_r,t,limits)
```
r is power balancing authority; revisions use two immutable issue-time snapshots; hedge maps only to liquid related assets with modeled cross-basis.
**Capacity and eligibility:** Trade via highly liquid gas futures or energy equity baskets, with geographic basis and sector beta mismatch priced.
Unspecified coefficients must be estimated only from training windows and no undocumented constraint may be relaxed.

## Source, clock and data contract
NWS issued and archived forecasts, EIA balancing authority hourly load and generation, power/gas futures settlements and basis. **Observation grain:** balancing authority × weather forecast issuance × lead hour. **Decision horizon:** forecast issuance is the earliest legal decision; never consume later realized weather or EIA actual load before release.
At minimum require `observation_id`, `effective_at`, `published_at`, `available_at`, `ingested_at`, `source_uri`, `license_class`, `revision_id`, `unit`. `available_at <= decision_time` is mandatory for all market signals. New revisions create new records and must not silently overwrite historical decisions.

## Functional and nonfunctional requirements
| ID | Explicit requirement | Priority |
|---|---|---|
| REQ-001 | Model the permitted choice: Size gas/power-linked hedges using only prior-issued weather forecasts and expected net-load revisions. | Must |
| REQ-002 | Reproduce feasible benchmark: Seasonal degree-day demand regression and absolute temperature forecasts. | Must |
| REQ-003 | Implement candidate Net-load forecast-revision elasticity with non-linear stress threshold. only after benchmark | Must |
| REQ-004 | Report load p95 quantile loss, probabilistic calibration, hedge tracking error, net futures carry. and matched capacity/execution economics | Must |
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
USD $170k hypothetical 24-month engineering/data/maintenance cost; gross benefit sensitivity $0k–$470k over 24 months. Net ROI = (gross benefit − cost)/cost = **-100% to 176%**. NOT forecast or historical measurement. Economic lever: hypothetical $10m energy risk sleeve with 0–235 bps annualized risk/carry improvements; outcomes uncertain.. Source availability: NWS API provides forecasts; EIA provides actual hourly grid operation data; forecast version history must be separately collected going forward.
Funding, transaction cost and execution constraints require separate real calibration.

## Primary risks and negative gates
- **RISK-001:** Archive of *historical forecasts as issued* may be inaccessible; today's historical observations are not contemporaneous forecasts.
- **RISK-002:** Data sparsity, nonstationarity, multiple testing and selection effects.
- **RISK-003:** Rights, settlement or investability restrictions may make an apparent opportunity infeasible.
- **Predeclared stop:** Reject if no improvements in forecast quantile loss or hedge after-cost variance over degrees-day baseline.
- **Non-goals:** Trading, legal/compliance approvals, publishing real P&L, or deployment from this spec alone.
