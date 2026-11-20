# SPEC — Global Shipping Connectivity Re-Routing to Inflation and Equity Margins
**ID:** QMG-20261120-15 · **Category:** DOMESTIC & GLOBAL MARKETS · **Status:** DRAFT; empirical verification BLOCKED.
## Economic question and decision
Freight disruption signals are often conflated with trade quantities, while shipping network redundancy alters price transmission under port outages. Decision: Size logistics/inflation hedges when public route connectivity and port-service centrality shift.
- **H1:** Route-centrality-adjusted connectivity changes improve delayed goods-inflation and shipper-margin forecasts over raw container volume.
- **H0:** Supply-route network exposure local projections does not improve after-cost decision performance over Aggregate global shipping index versus region CPI with fixed lag.
## Formulation and constraints
```text
DeltaP_{r,t+h}=sum_p Exposure_{r,p}*Shock_{p,t}/(1+AlternateRoutes_{p,t})+epsilon
```
r is importer region, p port corridor; shocks and alternate route count must use actually published index vintage.
## Observation contract and time boundaries
**Grain:** country/port route × monthly index release × subsequent inflation/earnings outcome. **Fields:** UNCTAD monthly/quarterly liner connectivity, MARAD freight/port dashboards, shipping rate indexes where licensed, CPI/PPI and issuer logistics costs.. **Availability:** UNCTAD latest confirmed index data update Sep 28 2026; a 2026-11-20 decision cannot use December data..
Every input must carry `source_id, market, instrument_id, effective_at_utc, observed_at_utc, published_at_utc, available_at_utc, ingested_at_utc, immutable_revision_id, license_class`. Decision features may use only rows with `available_at_utc<=decision_at_utc`. Build synthetic examples when licensed data unavailable.
## Testable requirements
| ID | Requirement | Acceptance |
|---|---|---|
| REQ-001 | Form a legally feasible East Asia–Europe–US maritime routes, transport/industrial equity sectors decision before action clock. | AC-001: reject stale/unknown/ineligible inputs |
| REQ-002 | Reconstruct `Aggregate global shipping index versus region CPI with fixed lag` with full cost and opportunity matching. | AC-002: deterministic fixture replicates baseline |
| REQ-003 | Reproduce `Supply-route network exposure local projections` on frozen train and later holdout. | AC-003: no future features or post-selection |
| REQ-004 | Report `inflation nowcast gain, equity margin dispersion, attribution stability and hedged net P&L` with implementation loss. | AC-004: controlled uncertainty and capacity results |
| NFR-001 | Durable logs, lineage, source rights and reproducibility. | AC-005: positive/negative tests and locked versions |
| NFR-002 | No automatic trade, contract/legal interpretation or restricted disclosure. | AC-006: block unauthorized action |
## Hard no-go tests
**Confounding/leakage:** Connectivity is not real-time port congestion and quarterly updates can obscure freight cycle timing.
**Falsification:** No incremental signal after global industrial production, oil and published trade volume controls.
**Production constraints:** Sector ETF/futures depth, global market close mismatch, FX hedge and rebalance slippage.
**Economic scenario (not a forecast):** $220k hypothetical total 24-month labor/data/compute/compliance cost; rollout begins after 10 months; annual gross benefit scenarios $0k / $135k / $300k (downside/base/upside) for the remaining 1.1666666666666667 years. Net ROI=(benefit×active years−cost)/cost = -100.0% / -28.4% / 59.1%. These figures are scenario *assumptions*, not expected value, observed alpha, institutional revenue, or forward predictions.
## Non-goals
No confidential inputs, deployed strategy, compliance opinion, broker action or genuine 24-month ROI measurement is provided.
