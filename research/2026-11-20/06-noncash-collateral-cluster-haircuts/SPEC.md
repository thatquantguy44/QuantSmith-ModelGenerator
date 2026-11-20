# SPEC — Noncash Collateral Correlation-Cluster Haircut Controller
**ID:** QMG-20261120-06 · **Category:** SECURITIES FINANCE · **Status:** DRAFT; empirical verification BLOCKED.
## Economic question and decision
Static issuer/security-class haircuts can understate simultaneous stress of correlated noncash collateral while overhaircutting diversified pools. Decision: Recommend minimum defensive haircuts for a collateral basket based on joint concentration and liquidation correlation.
- **H1:** Cluster-aware chance constraints produce lower stressed shortfall than sector-flat haircuts at a matched average financing cost.
- **H0:** Scenario CVaR optimization with issuer cluster caps does not improve after-cost decision performance over Uniform issuer/asset-class static haircut.
## Formulation and constraints
```text
min_h CarryCost(h) subject to P(Loss(Collateral,Loan,h)>Limit)<=alpha and issuer_weight<=cap
```
h is haircut vector, alpha tolerated tail probability and cap issuer concentration; credit/legal eligibility are hard constraints.
## Observation contract and time boundaries
**Grain:** collateral security × issuer cluster × loan exposure × as-of time. **Fields:** Approved collateral constituents, synthetic issuer cross-holdings, stressed factor returns, liquidation bid/ask, haircut and legal threshold.. **Availability:** Apply only return histories, prices, group linkages and issuer memberships known at the decision timestamp..
Every input must carry `source_id, market, instrument_id, effective_at_utc, observed_at_utc, published_at_utc, available_at_utc, ingested_at_utc, immutable_revision_id, license_class`. Decision features may use only rows with `available_at_utc<=decision_at_utc`. Build synthetic examples when licensed data unavailable.
## Testable requirements
| ID | Requirement | Acceptance |
|---|---|---|
| REQ-001 | Form a legally feasible Multi-asset collateral supporting US/EU securities loans decision before action clock. | AC-001: reject stale/unknown/ineligible inputs |
| REQ-002 | Reconstruct `Uniform issuer/asset-class static haircut` with full cost and opportunity matching. | AC-002: deterministic fixture replicates baseline |
| REQ-003 | Reproduce `Scenario CVaR optimization with issuer cluster caps` on frozen train and later holdout. | AC-003: no future features or post-selection |
| REQ-004 | Report `shortfall ES, collateral usage, haircut turnover, stress exceptions` with implementation loss. | AC-004: controlled uncertainty and capacity results |
| NFR-001 | Durable logs, lineage, source rights and reproducibility. | AC-005: positive/negative tests and locked versions |
| NFR-002 | No automatic trade, contract/legal interpretation or restricted disclosure. | AC-006: block unauthorized action |
## Hard no-go tests
**Confounding/leakage:** Asset covariance may break exactly when haircuts are needed and public free-float proxies omit liquidation controls.
**Falsification:** Risk benefit disappears when using stressed-correlation holdouts or violates legal haircut floors.
**Production constraints:** Financing spread effects, haircuts, asset transfer restrictions, concentration penalties and market impact.
**Economic scenario (not a forecast):** $210k hypothetical total 24-month labor/data/compute/compliance cost; rollout begins after 9 months; annual gross benefit scenarios $0k / $145k / $320k (downside/base/upside) for the remaining 1.25 years. Net ROI=(benefit×active years−cost)/cost = -100.0% / -13.7% / 90.5%. These figures are scenario *assumptions*, not expected value, observed alpha, institutional revenue, or forward predictions.
## Non-goals
No confidential inputs, deployed strategy, compliance opinion, broker action or genuine 24-month ROI measurement is provided.
