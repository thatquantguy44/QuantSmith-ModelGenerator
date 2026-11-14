# SPEC — Trade-Network Export-Shock Transmission to Equity Sectors
**ID:** QMG-20261113-11 · **Status:** Draft; human approval required · **Category:** B · Domestic & global markets · **Geography:** US, Mexico, Germany, Japan, Korea, China and ASEAN markets

## Problem and decision
Changes in bilateral product-level exports are not evenly distributed: input-output bottlenecks may propagate to equity sectors before aggregate macro summaries appear.
**Decision supported:** Adjust public-market sector risk or hedges using time-valid trade-network concentration shocks, not a blunt GDP exposure factor.

## H1 versus H0
**H1:** Lag-aware product-network shocks identify medium-horizon cross-country sector earnings surprises beyond FX and industrial production.
**H0:** A cost-inclusive Equal-weight country sector allocation with FX and local industrial production controls. matches or exceeds the candidate on strictly out-of-sample decisions. The intent is falsification, not confirmation.

## Mathematical problem and domain
```text
Shock_(c,k,t)=Σ_p upstream_weight_(c,k,p)*Δexports_(p,t); alpha_(sector,t+h)=β*Shock_available_t - controls
```
c is country, k sector, p harmonized product/trade edge, h a preselected post-publication investment horizon.
**Capacity and eligibility:** ETFs and liquid futures only for first implementation; portfolio turnover caps and country exposure floors.
Unspecified coefficients must be estimated only from training windows and no undocumented constraint may be relaxed.

## Source, clock and data contract
UN Comtrade reported and partner-reported trade by HS code/month; sector country revenue mix; FX; sector returns and macro controls. **Observation grain:** reporter × partner × HS code × reference month × publication/availability timestamp. **Decision horizon:** monthly after trade report publication and revision; NEVER trade at reference-month timestamp.
At minimum require `observation_id`, `effective_at`, `published_at`, `available_at`, `ingested_at`, `source_uri`, `license_class`, `revision_id`, `unit`. `available_at <= decision_time` is mandatory for all market signals. New revisions create new records and must not silently overwrite historical decisions.

## Functional and nonfunctional requirements
| ID | Explicit requirement | Priority |
|---|---|---|
| REQ-001 | Model the permitted choice: Adjust public-market sector risk or hedges using time-valid trade-network concentration shocks, not a blunt GDP exposure factor. | Must |
| REQ-002 | Reproduce feasible benchmark: Equal-weight country sector allocation with FX and local industrial production controls. | Must |
| REQ-003 | Implement candidate Sparse directed trade graph factor with event-lag-aware regressions. only after benchmark | Must |
| REQ-004 | Report OOS sector information coefficient, dollar-neutral Sharpe, earnings revision hit rate, turnover and tail loss. and matched capacity/execution economics | Must |
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
USD $150k hypothetical 24-month engineering/data/maintenance cost; gross benefit sensitivity $0k–$520k over 24 months. Net ROI = (gross benefit − cost)/cost = **-100% to 247%**. NOT forecast or historical measurement. Economic lever: hypothetical $10m liquid sector sleeve and 0–260 bps gross annualized alpha capture over 2 years; zero base benefit is plausible.. Source availability: UN Comtrade public preview has limited records; full historical coverage may require free keyed or premium bulk access.
Funding, transaction cost and execution constraints require separate real calibration.

## Primary risks and negative gates
- **RISK-001:** Revisions, late reporters, trade re-exports and mapping HS codes to listed firms can create survivorship and spurious exposure.
- **RISK-002:** Data sparsity, nonstationarity, multiple testing and selection effects.
- **RISK-003:** Rights, settlement or investability restrictions may make an apparent opportunity infeasible.
- **Predeclared stop:** Reject if positive net cross-country IC is not stable in each of two disjoint geographic holdouts or after publication lags.
- **Non-goals:** Trading, legal/compliance approvals, publishing real P&L, or deployment from this spec alone.
