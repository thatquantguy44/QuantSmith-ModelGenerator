# SPEC — Treasury Issuance-to-Dealer Intermediation Capacity Map
**ID:** QMG-20261113-09 · **Status:** Draft; human approval required · **Category:** A · Securities finance · **Geography:** United States issuance and dealer system

## Problem and decision
New issuance and benchmark rollovers impose inventory absorption on dealer balance sheets; public positioning snapshots may reveal when the marginal intermediation cost rises.
**Decision supported:** Set research-level short-term Treasury liquidity stress overlays around security supply events, independent of day-of-quarter calendar effects.

## H1 versus H0
**H1:** Public auction-supply and weekly dealer-position innovations predict future Treasury liquidity stress more reliably than rate volatility alone.
**H0:** A cost-inclusive Treasury yield volatility and calendar week indicators. matches or exceeds the candidate on strictly out-of-sample decisions. The intent is falsification, not confirmation.

## Mathematical problem and domain
```text
C_t=Δissuance_t - β*Δdealer_financed_positions_t; p_(t+h)=sigmoid(α+γ*C_(available≤t)+δ*vol_t)
```
C_t is an issuance-absorption mismatch proxy, not observed dealer capital; p is stress probability, h is pre-set future horizon.
**Capacity and eligibility:** Public signal is a risk overlay; tradability needs actual Treasury order book, bid/ask, duration and repo access.
Unspecified coefficients must be estimated only from training windows and no undocumented constraint may be relaxed.

## Source, clock and data contract
Treasury auction issuance and settlement schedule; weekly primary dealer net positions/financing; OFR repo aggregates; public Treasury yield changes. **Observation grain:** issuance cohort × week of publicly released dealer aggregates. **Decision horizon:** weekly close after primary dealer publication; never treat reported prior-week positions as contemporaneous.
At minimum require `observation_id`, `effective_at`, `published_at`, `available_at`, `ingested_at`, `source_uri`, `license_class`, `revision_id`, `unit`. `available_at <= decision_time` is mandatory for all market signals. New revisions create new records and must not silently overwrite historical decisions.

## Functional and nonfunctional requirements
| ID | Explicit requirement | Priority |
|---|---|---|
| REQ-001 | Model the permitted choice: Set research-level short-term Treasury liquidity stress overlays around security supply events, independent of day-of-quarter calendar effects. | Must |
| REQ-002 | Reproduce feasible benchmark: Treasury yield volatility and calendar week indicators. | Must |
| REQ-003 | Implement candidate Event-study + state-space dealer supply absorption proxy. only after benchmark | Must |
| REQ-004 | Report stress forecast Brier, AUPRC, lead-time, false positives and hedge drawdown. and matched capacity/execution economics | Must |
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
USD $100k hypothetical 24-month engineering/data/maintenance cost; gross benefit sensitivity $25k–$170k over 24 months. Net ROI = (gross benefit − cost)/cost = **-75% to 70%**. NOT forecast or historical measurement. Economic lever: scenario: one avoided bad inventory allocation month or improved hedging stress alerts; not a measured signal.. Source availability: Treasury and NY Fed release events and dealer statistics publicly, though publication lags must be retained.
Funding, transaction cost and execution constraints require separate real calibration.

## Primary risks and negative gates
- **RISK-001:** Aggregate dealer reports cannot identify securities or dealers and issuance is endogenous to financing conditions.
- **RISK-002:** Data sparsity, nonstationarity, multiple testing and selection effects.
- **RISK-003:** Rights, settlement or investability restrictions may make an apparent opportunity infeasible.
- **Predeclared stop:** Reject if no improvement over the rate-volatility-only benchmark on genuinely held-out issuance regimes.
- **Non-goals:** Trading, legal/compliance approvals, publishing real P&L, or deployment from this spec alone.
