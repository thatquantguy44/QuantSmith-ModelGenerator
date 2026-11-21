# SPEC — Wheat Export Inspection Revisions to Global Basis and Calendar Spreads
**ID:** QMG-20261120-18 · **Category:** DOMESTIC & GLOBAL MARKETS · **Status:** DRAFT; empirical verification BLOCKED.
## Economic question and decision
Weekly port inspection momentum and monthly USDA supply tables arrive at different times and may contain meaningful revisions. Decision: Hedge wheat calendar spreads around official export inspection versus world balance-sheet information releases.
- **H1:** Vintage-corrected inspection surprises anticipate regional wheat basis and nearby-deferred spread movements beyond seasonality and WASDE.
- **H0:** Mixed-frequency distributed-lag export surprise model does not improve after-cost decision performance over Monthly seasonal wheat spread regression using last known WASDE.
## Formulation and constraints
```text
BasisChange_{r,t+h}=alpha+beta*(InspectionsPublished_t-ExpectedInspections_t)+gamma*Weather_t+epsilon
```
r region; expected inspections estimated using only pre-release history; h is post-release decision horizon with realistic market access.
## Observation contract and time boundaries
**Grain:** weekly USDA inspection release × grain class × destination × exchange quote timestamp. **Fields:** USDA AMS export grain inspections dashboard, USDA wheat supply/price tables, official crop calendars, futures curves and export policy announcement records.. **Availability:** USDA dashboard launched Oct 14 2026 and wheat tables updated Nov 12 2026; do not replace historic reports with latest annual revisions..
Every input must carry `source_id, market, instrument_id, effective_at_utc, observed_at_utc, published_at_utc, available_at_utc, ingested_at_utc, immutable_revision_id, license_class`. Decision features may use only rows with `available_at_utc<=decision_at_utc`. Build synthetic examples when licensed data unavailable.
## Testable requirements
| ID | Requirement | Acceptance |
|---|---|---|
| REQ-001 | Form a legally feasible US, Black Sea and international wheat futures/physical flows decision before action clock. | AC-001: reject stale/unknown/ineligible inputs |
| REQ-002 | Reconstruct `Monthly seasonal wheat spread regression using last known WASDE` with full cost and opportunity matching. | AC-002: deterministic fixture replicates baseline |
| REQ-003 | Reproduce `Mixed-frequency distributed-lag export surprise model` on frozen train and later holdout. | AC-003: no future features or post-selection |
| REQ-004 | Report `spread forecast delta, regional basis tracking, net slippage-adjusted hedge P&L, regime robustness` with implementation loss. | AC-004: controlled uncertainty and capacity results |
| NFR-001 | Durable logs, lineage, source rights and reproducibility. | AC-005: positive/negative tests and locked versions |
| NFR-002 | No automatic trade, contract/legal interpretation or restricted disclosure. | AC-006: block unauthorized action |
## Hard no-go tests
**Confounding/leakage:** Weekly inspections differ from actual export commitments; Black Sea supply and policy announcements may dominate.
**Falsification:** No predictive improvement after weather, futures calendar effects and contemporaneous official release lags.
**Production constraints:** CME wheat futures tick, spread roll, physical basis accessibility and region transport costs.
**Economic scenario (not a forecast):** $175k hypothetical total 24-month labor/data/compute/compliance cost; rollout begins after 9 months; annual gross benefit scenarios $0k / $100k / $265k (downside/base/upside) for the remaining 1.25 years. Net ROI=(benefit×active years−cost)/cost = -100.0% / -28.6% / 89.3%. These figures are scenario *assumptions*, not expected value, observed alpha, institutional revenue, or forward predictions.
## Non-goals
No confidential inputs, deployed strategy, compliance opinion, broker action or genuine 24-month ROI measurement is provided.
