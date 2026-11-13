# SPEC — AI Infrastructure Capex-to-Power-and-Export Supply Chain Factor
**ID:** QMG-20261113-14 · **Status:** Draft; human approval required · **Category:** B · Domestic & global markets · **Geography:** United States, Taiwan, South Korea, Singapore and Malaysia

## Problem and decision
Corporate capex plans for AI facilities may not translate into actual compute deployments until grids, transformers, electric generation and overseas component exports clear physical bottlenecks.
**Decision supported:** Construct capacity-confirmation exposures instead of mechanically buying companies mentioning AI investment.

## H1 versus H0
**H1:** Public capex-to-power-to-export bottleneck signals predict medium-horizon revisions across semiconductor equipment, utilities and data-center supply chains.
**H0:** A cost-inclusive Equal-weight US tech/utility/semiconductor thematic basket with broad market hedge. matches or exceeds the candidate on strictly out-of-sample decisions. The intent is falsification, not confirmation.

## Mathematical problem and domain
```text
Bottleneck_t = min(grid_capacity_t/expected_load_t, export_supply_t/needed_components_t); signal_i,t=exposure_i*(Bottleneck_t-1)
```
expected_load and needed_components are explicit assumptions, not observable facts; no inferral of private company data-center locations.
**Capacity and eligibility:** Cap exposure to liquid industry ETFs/stocks; forecast vintages and reasonable turnover restrictions.
Unspecified coefficients must be estimated only from training windows and no undocumented constraint may be relaxed.

## Source, clock and data contract
SEC EDGAR filed capital expenditure and commitments, EIA power demand/generation, public utility service-area reports, UN Comtrade semiconductor/electrical equipment trade. **Observation grain:** public company disclosure × filing-time vintage × geography × monthly energy/trade release. **Decision horizon:** rebalance monthly after latest public filings, energy updates and international trade release.
At minimum require `observation_id`, `effective_at`, `published_at`, `available_at`, `ingested_at`, `source_uri`, `license_class`, `revision_id`, `unit`. `available_at <= decision_time` is mandatory for all market signals. New revisions create new records and must not silently overwrite historical decisions.

## Functional and nonfunctional requirements
| ID | Explicit requirement | Priority |
|---|---|---|
| REQ-001 | Model the permitted choice: Construct capacity-confirmation exposures instead of mechanically buying companies mentioning AI investment. | Must |
| REQ-002 | Reproduce feasible benchmark: Equal-weight US tech/utility/semiconductor thematic basket with broad market hedge. | Must |
| REQ-003 | Implement candidate Supply-chain bottleneck score anchored in publicly observed physical constraints. only after benchmark | Must |
| REQ-004 | Report sector-neutral residual return, realized earnings revision, stock/industry turnover and capacity sensitivity. and matched capacity/execution economics | Must |
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
USD $180k hypothetical 24-month engineering/data/maintenance cost; gross benefit sensitivity $0k–$560k over 24 months. Net ROI = (gross benefit − cost)/cost = **-100% to 211%**. NOT forecast or historical measurement. Economic lever: hypothetical $15m thematic sleeve; 0–185 bps annualized incremental after-cost return within favorable scenario; zero benefit base case.. Source availability: SEC filing disclosures, EIA grid observations and UN Comtrade aggregate products; issuer-level mapping is research inference.
Funding, transaction cost and execution constraints require separate real calibration.

## Primary risks and negative gates
- **RISK-001:** Disclosure boilerplate, future guidance and partial energy-grid footprint can generate strong hindsight mapping bias.
- **RISK-002:** Data sparsity, nonstationarity, multiple testing and selection effects.
- **RISK-003:** Rights, settlement or investability restrictions may make an apparent opportunity infeasible.
- **Predeclared stop:** Reject if holdout earnings-revision association and after-cost portfolio uplift vanish after mega-cap momentum controls.
- **Non-goals:** Trading, legal/compliance approvals, publishing real P&L, or deployment from this spec alone.
