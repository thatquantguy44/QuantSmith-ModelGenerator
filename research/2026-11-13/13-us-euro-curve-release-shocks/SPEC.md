# SPEC — US–Euro Sovereign Curve Shock Decomposition with Data Vintages
**ID:** QMG-20261113-13 · **Status:** Draft; human approval required · **Category:** B · Domestic & global markets · **Geography:** United States and euro area

## Problem and decision
US and euro curve co-movement can come from common real-rate news, term-premium repricing or currency-hedged spillovers; identical correlations mask distinct hedge choices.
**Decision supported:** Allocate DV01-neutral rates hedge exposure between US and European curve tenors after releases, subject to actual market liquidity.

## H1 versus H0
**H1:** Vintaged macro-announcement decomposition reduces out-of-sample cross-market duration hedge error versus rolling beta.
**H0:** A cost-inclusive 60-day rolling DV01-neutral cross-market beta hedge. matches or exceeds the candidate on strictly out-of-sample decisions. The intent is falsification, not confirmation.

## Mathematical problem and domain
```text
Δy_US,t = β1*Surprise_US,t + β2*Surprise_EU,t + u_t; h*=argmin_h E[(ΔP_US+h*ΔP_EU)^2]+turnover_cost(h)
```
y is sovereign yield; Surprise is actual release minus consensus known beforehand (consensus may require licensing); h is DV01-scaled hedge.
**Capacity and eligibility:** Restrict first pass to liquid Treasury/Bund futures and realistic FX basis and futures trading costs.
Unspecified coefficients must be estimated only from training windows and no undocumented constraint may be relaxed.

## Source, clock and data contract
ECB published euro yield curve, US yields and ALFRED macro vintages, official release times, FX hedges, rates futures cost. **Observation grain:** economic release event × curve tenor × publication instant × geography. **Decision horizon:** end-of-release or next-session decision after releases disseminate; avoid falsely assuming instant access to revised series.
At minimum require `observation_id`, `effective_at`, `published_at`, `available_at`, `ingested_at`, `source_uri`, `license_class`, `revision_id`, `unit`. `available_at <= decision_time` is mandatory for all market signals. New revisions create new records and must not silently overwrite historical decisions.

## Functional and nonfunctional requirements
| ID | Explicit requirement | Priority |
|---|---|---|
| REQ-001 | Model the permitted choice: Allocate DV01-neutral rates hedge exposure between US and European curve tenors after releases, subject to actual market liquidity. | Must |
| REQ-002 | Reproduce feasible benchmark: 60-day rolling DV01-neutral cross-market beta hedge. | Must |
| REQ-003 | Implement candidate Vintaged announcement factor model plus shrinkage hedge weights. only after benchmark | Must |
| REQ-004 | Report OOS hedging variance reduction, implementation shortfall, tail DV01 loss, signal turnover. and matched capacity/execution economics | Must |
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
USD $165k hypothetical 24-month engineering/data/maintenance cost; gross benefit sensitivity $0k–$355k over 24 months. Net ROI = (gross benefit − cost)/cost = **-100% to 115%**. NOT forecast or historical measurement. Economic lever: hypothetical $25m DV01-managed hedge sleeve with 0–120 bps equivalent annualized cost/risk improvement; not a backtest.. Source availability: ECB and FRED provide curves/vintages but not executable futures bid/ask or consensus expectation snapshots.
Funding, transaction cost and execution constraints require separate real calibration.

## Primary risks and negative gates
- **RISK-001:** Public releases cannot recreate market consensus surprises without a licensed historical consensus dataset or explicit no-consensus baseline.
- **RISK-002:** Data sparsity, nonstationarity, multiple testing and selection effects.
- **RISK-003:** Rights, settlement or investability restrictions may make an apparent opportunity infeasible.
- **Predeclared stop:** Reject if hedge variance does not improve at least 5% net of turnover on independent event holdout.
- **Non-goals:** Trading, legal/compliance approvals, publishing real P&L, or deployment from this spec alone.
