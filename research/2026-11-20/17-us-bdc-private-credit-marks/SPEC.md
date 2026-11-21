# SPEC — Public BDC Portfolio Fair-Value Markdown Lead Indicator
**ID:** QMG-20261120-17 · **Category:** DOMESTIC & GLOBAL MARKETS · **Status:** DRAFT; empirical verification BLOCKED.
## Economic question and decision
Quarterly fair values of less-liquid loans are not continuous market prices; comparability and valuation lag impair credit monitoring. Decision: Prioritize due diligence or credit hedges where public business development company holdings imply delayed loan fair-value marks.
- **H1:** Public issuer-level BDC portfolio mark dispersion identifies future credit event/downgrade risk after controlling for BDC leverage and macro credit spread.
- **H0:** Issuer-level mark-hazard panel with censored holdings and missing-not-at-random controls does not improve after-cost decision performance over BDC aggregate NAV discount and published nonaccrual percentage.
## Formulation and constraints
```text
RiskScore_{loan,t}=f(PriceToCost_{t},NonAccrual_{t},Sector_{t},FundLag_{t})
```
PriceToCost is reported fair value over cost, nonaccrual flags only as filed, FundLag is filing delay; target is future externally validated credit deterioration.
## Observation contract and time boundaries
**Grain:** BDC filing × portfolio company/sector × disclosure timestamp. **Fields:** Original SEC BDC 10-Q/10-K investment schedules and mark values, sector classification, publicly known credit outcomes and licensed leveraged-loan pricing.. **Availability:** Use filed investment schedules only after filing acceptance; amendments/revised portfolio marks cannot enter historical quarters..
Every input must carry `source_id, market, instrument_id, effective_at_utc, observed_at_utc, published_at_utc, available_at_utc, ingested_at_utc, immutable_revision_id, license_class`. Decision features may use only rows with `available_at_utc<=decision_at_utc`. Build synthetic examples when licensed data unavailable.
## Testable requirements
| ID | Requirement | Acceptance |
|---|---|---|
| REQ-001 | Form a legally feasible US public BDC equities, leveraged loans and credit sentiment decision before action clock. | AC-001: reject stale/unknown/ineligible inputs |
| REQ-002 | Reconstruct `BDC aggregate NAV discount and published nonaccrual percentage` with full cost and opportunity matching. | AC-002: deterministic fixture replicates baseline |
| REQ-003 | Reproduce `Issuer-level mark-hazard panel with censored holdings and missing-not-at-random controls` on frozen train and later holdout. | AC-003: no future features or post-selection |
| REQ-004 | Report `future credit-event AUC/PR, mark-calibration error, NAV stress accuracy, opportunity capacity` with implementation loss. | AC-004: controlled uncertainty and capacity results |
| NFR-001 | Durable logs, lineage, source rights and reproducibility. | AC-005: positive/negative tests and locked versions |
| NFR-002 | No automatic trade, contract/legal interpretation or restricted disclosure. | AC-006: block unauthorized action |
## Hard no-go tests
**Confounding/leakage:** BDC portfolio company identities, valuation methods and distressed sales are not uniformly disclosed; matching bias.
**Falsification:** No improvement over current NAV discount/nonaccrual baseline in later quarters or effects only known after financial reports.
**Production constraints:** BDC equity market depth, credit hedging basis, optional loan trading access and stale valuation discounts.
**Economic scenario (not a forecast):** $190k hypothetical total 24-month labor/data/compute/compliance cost; rollout begins after 10 months; annual gross benefit scenarios $0k / $115k / $275k (downside/base/upside) for the remaining 1.1666666666666667 years. Net ROI=(benefit×active years−cost)/cost = -100.0% / -29.4% / 68.9%. These figures are scenario *assumptions*, not expected value, observed alpha, institutional revenue, or forward predictions.
## Non-goals
No confidential inputs, deployed strategy, compliance opinion, broker action or genuine 24-month ROI measurement is provided.
