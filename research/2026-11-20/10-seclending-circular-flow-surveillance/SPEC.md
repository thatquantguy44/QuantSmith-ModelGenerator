# SPEC — Securities-Lending Circular Flow Surveillance via Temporal Graphs
**ID:** QMG-20261120-10 · **Category:** SECURITIES FINANCE · **Status:** DRAFT; empirical verification BLOCKED.
## Economic question and decision
Pairwise exception rules can miss cyclic chains of small loans and rapid reversals through multiple legal counterparties. Decision: Escalate suspicious short-lived circular borrow/return patterns for compliance review without inferring wrongdoing from volume alone.
- **H1:** Causal temporal-motif alerts improve precision at fixed review capacity over pairwise round-trip thresholds in seeded synthetic cases.
- **H0:** Temporal graph motif detection with exact deterministic event identity does not improve after-cost decision performance over Two-party net-quantity turnaround rules.
## Formulation and constraints
```text
min_alertPolicy ReviewCost + MissCost subject to ReviewCapacity<=K and no autonomously adverse action
```
K is review budget; temporal motif score must be conditioned on legitimate inventory transfers and settlement cycles.
## Observation contract and time boundaries
**Grain:** synthetic securities loan transfer edge × security × event timestamp. **Fields:** Synthetic multi-party loan/return event graph, matched collateral movement, legitimate transfer controls, anonymized case annotations if permitted.. **Availability:** Create graph only from recorded transfers visible before alert time; disallow knowledge of subsequent investigation outcomes in features..
Every input must carry `source_id, market, instrument_id, effective_at_utc, observed_at_utc, published_at_utc, available_at_utc, ingested_at_utc, immutable_revision_id, license_class`. Decision features may use only rows with `available_at_utc<=decision_at_utc`. Build synthetic examples when licensed data unavailable.
## Testable requirements
| ID | Requirement | Acceptance |
|---|---|---|
| REQ-001 | Form a legally feasible Multi-agent securities loans and collateral transfers; US/EU decision before action clock. | AC-001: reject stale/unknown/ineligible inputs |
| REQ-002 | Reconstruct `Two-party net-quantity turnaround rules` with full cost and opportunity matching. | AC-002: deterministic fixture replicates baseline |
| REQ-003 | Reproduce `Temporal graph motif detection with exact deterministic event identity` on frozen train and later holdout. | AC-003: no future features or post-selection |
| REQ-004 | Report `precision at K, seeded motif recall, legitimate-flow false-alerts, explanation fidelity` with implementation loss. | AC-004: controlled uncertainty and capacity results |
| NFR-001 | Durable logs, lineage, source rights and reproducibility. | AC-005: positive/negative tests and locked versions |
| NFR-002 | No automatic trade, contract/legal interpretation or restricted disclosure. | AC-006: block unauthorized action |
## Hard no-go tests
**Confounding/leakage:** False accusations, privileged customer data, and severe sample-selection bias in investigated cases.
**Falsification:** No precision@K gain against pairwise rules under benign high-volume churn fixtures.
**Production constraints:** Compliance analyst review capacity and evidentiary retention, no automatic client suspension.
**Economic scenario (not a forecast):** $165k hypothetical total 24-month labor/data/compute/compliance cost; rollout begins after 9 months; annual gross benefit scenarios $0k / $95k / $240k (downside/base/upside) for the remaining 1.25 years. Net ROI=(benefit×active years−cost)/cost = -100.0% / -28.0% / 81.8%. These figures are scenario *assumptions*, not expected value, observed alpha, institutional revenue, or forward predictions.
## Non-goals
No confidential inputs, deployed strategy, compliance opinion, broker action or genuine 24-month ROI measurement is provided.
