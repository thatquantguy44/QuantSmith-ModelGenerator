# SPEC — CFTC Positioning Concentration and Commodity Curve Convexity
**ID:** QMG-20261113-15 · **Status:** Draft; human approval required · **Category:** B · Domestic & global markets · **Geography:** United States commodity futures with global supply chains

## Problem and decision
Speculator long/short crowding alone is a weak factor; crowding combined with curve convexity and roll liquidity may identify asymmetric liquidation windows.
**Decision supported:** Scale futures trend/curve exposure after weekly public positioning releases with pre-set liquidation budgets.

## H1 versus H0
**H1:** CFTC public trader-category concentration interacts with futures curve slope/convexity to forecast downside tail asymmetry better than carry alone.
**H0:** A cost-inclusive Futures curve carry/roll-yield and 12-month time-series momentum. matches or exceeds the candidate on strictly out-of-sample decisions. The intent is falsification, not confirmation.

## Mathematical problem and domain
```text
Crowding_t=(spec_long_t-spec_short_t)/OI_t; Convexity_t=F1_t-2F2_t+F3_t; TailScore_t=β*Crowding_t*Convexity_t
```
F1..F3 are aligned futures maturities with explicit roll rules; OI is the reported futures open interest, all at publication availability.
**Capacity and eligibility:** Enforce futures open interest participation cap, roll liquidity and margin stress; no physical commodity positions.
Unspecified coefficients must be estimated only from training windows and no undocumented constraint may be relaxed.

## Source, clock and data contract
CFTC Disaggregated COT futures positions, futures contracts prices/rolls, EIA physical inventories where applicable. **Observation grain:** CFTC contract market × Tuesday reference position × Friday public release, then weekly trade clock. **Decision horizon:** earliest action is CFTC publication/next executable session; no use of Tuesday positions on Tuesday.
At minimum require `observation_id`, `effective_at`, `published_at`, `available_at`, `ingested_at`, `source_uri`, `license_class`, `revision_id`, `unit`. `available_at <= decision_time` is mandatory for all market signals. New revisions create new records and must not silently overwrite historical decisions.

## Functional and nonfunctional requirements
| ID | Explicit requirement | Priority |
|---|---|---|
| REQ-001 | Model the permitted choice: Scale futures trend/curve exposure after weekly public positioning releases with pre-set liquidation budgets. | Must |
| REQ-002 | Reproduce feasible benchmark: Futures curve carry/roll-yield and 12-month time-series momentum. | Must |
| REQ-003 | Implement candidate Positioning-conditioned conditional expected shortfall regression. only after benchmark | Must |
| REQ-004 | Report tail loss reduction, annualized Sharpe after roll/slippage, opportunity-cost drag and hedge stability. and matched capacity/execution economics | Must |
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
USD $105k hypothetical 24-month engineering/data/maintenance cost; gross benefit sensitivity $0k–$250k over 24 months. Net ROI = (gross benefit − cost)/cost = **-100% to 138%**. NOT forecast or historical measurement. Economic lever: hypothetical $20m risk budget, small tail-loss reduction in commodity futures over 24 months; benefits uncertain.. Source availability: CFTC public positioning has Tuesday reference dates and Friday releases; curve prices may be delayed/paid.
Funding, transaction cost and execution constraints require separate real calibration.

## Primary risks and negative gates
- **RISK-001:** CFTC taxonomy changes, combined report double-counting and slow publication may annihilate predictive edge.
- **RISK-002:** Data sparsity, nonstationarity, multiple testing and selection effects.
- **RISK-003:** Rights, settlement or investability restrictions may make an apparent opportunity infeasible.
- **Predeclared stop:** Reject if tail-risk control does not beat carry/momentum or negative convexity effect changes sign in out-of-sample contracts.
- **Non-goals:** Trading, legal/compliance approvals, publishing real P&L, or deployment from this spec alone.
