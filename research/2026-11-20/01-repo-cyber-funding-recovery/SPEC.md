# SPEC — Cyber-Outage Contingent Repo Funding Recovery Routes
**ID:** QMG-20261120-01 · **Category:** SECURITIES FINANCE · **Status:** DRAFT; empirical verification BLOCKED.
## Economic question and decision
A temporary lender or settlement-node cyber outage can strand otherwise sound secured funding even with sufficient collateral. Decision: Pre-approve alternate cash-lender/clearing routes and reserve a minimum contingency liquidity buffer for an exogenous operational outage.
- **H1:** Conditional multi-route recovery decreases funding shortfall and expected disruption cost more than an equal-cost static backup buffer.
- **H0:** Two-stage robust multi-commodity flow with cyber failure scenarios does not improve after-cost decision performance over Fixed 10% contingency funding buffer with one permitted fallback.
## Formulation and constraints
```text
min_{x,b} E_s[ FundingGap_s(x,b)*p_s + SwitchingCost_s(x) ] + CarryCost(b)
```
x are route and lender allocation decisions, b is reserved liquidity, p_s is the unit shortfall penalty in outage scenario s; legal availability, committed limits and collateral eligibility bound x.
## Observation contract and time boundaries
**Grain:** route × lender class × hourly outage scenario. **Fields:** Timestamped anonymized funding route uptime, fallback approvals, cutoff times, public OFR repo volumes/rates, synthetic outage schedules.. **Availability:** OFR cleared rate/volume normally T+1 and tri-party T+2, so use public series as lagged calibration only; route outage telemetry must be timestamped pre-decision..
Every input must carry `source_id, market, instrument_id, effective_at_utc, observed_at_utc, published_at_utc, available_at_utc, ingested_at_utc, immutable_revision_id, license_class`. Decision features may use only rows with `available_at_utc<=decision_at_utc`. Build synthetic examples when licensed data unavailable.
## Testable requirements
| ID | Requirement | Acceptance |
|---|---|---|
| REQ-001 | Form a legally feasible US cleared and tri-party repo decision before action clock. | AC-001: reject stale/unknown/ineligible inputs |
| REQ-002 | Reconstruct `Fixed 10% contingency funding buffer with one permitted fallback` with full cost and opportunity matching. | AC-002: deterministic fixture replicates baseline |
| REQ-003 | Reproduce `Two-stage robust multi-commodity flow with cyber failure scenarios` on frozen train and later holdout. | AC-003: no future features or post-selection |
| REQ-004 | Report `shortfall dollars, p95 duration, liquidity carry, fail probability, recovery cost` with implementation loss. | AC-004: controlled uncertainty and capacity results |
| NFR-001 | Durable logs, lineage, source rights and reproducibility. | AC-005: positive/negative tests and locked versions |
| NFR-002 | No automatic trade, contract/legal interpretation or restricted disclosure. | AC-006: block unauthorized action |
## Hard no-go tests
**Confounding/leakage:** Public aggregates cannot recover the bank-level cash-lender network or prove an actual route is legally available.
**Falsification:** Held-out synthetic/approved outage replay fails to reduce mean + tail shortfall at fixed total contingency cost.
**Production constraints:** Route/credit limits, settlement windows, cleared access and fallback switching charges; no publicly executable orders.
**Economic scenario (not a forecast):** $220k hypothetical total 24-month labor/data/compute/compliance cost; rollout begins after 9 months; annual gross benefit scenarios $0k / $180k / $340k (downside/base/upside) for the remaining 1.25 years. Net ROI=(benefit×active years−cost)/cost = -100.0% / 2.3% / 93.2%. These figures are scenario *assumptions*, not expected value, observed alpha, institutional revenue, or forward predictions.
## Non-goals
No confidential inputs, deployed strategy, compliance opinion, broker action or genuine 24-month ROI measurement is provided.
