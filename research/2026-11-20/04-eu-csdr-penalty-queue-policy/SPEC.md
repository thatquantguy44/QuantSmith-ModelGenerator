# SPEC — European CSDR Penalty-Aware Settlement Queue Prioritization
**ID:** QMG-20261120-04 · **Category:** SECURITIES FINANCE · **Status:** DRAFT; empirical verification BLOCKED.
## Economic question and decision
Unranked settlement queues may spend scarce intraday capacity on low-penalty legs while high-liability fails remain unresolved. Decision: Prioritize settlement instructions under explicit penalty eligibility and scarce processing resources.
- **H1:** A rule-aware queue policy lowers expected daily penalties and fail duration without worsening operational priority controls relative to FIFO.
- **H0:** Constrained weighted-shortest-processing-time queue policy with eligibility rules does not improve after-cost decision performance over FIFO or largest-notional-first allowed settlement priority.
## Formulation and constraints
```text
min_pi E[sum_i penalty_i*1(fail_i at close)+delay_cost_i] subject to legal_priority_i and capacity_t
```
pi is processing sequence, i instruction, penalty_i applies only under effective CSDR exclusions and jurisdictional rules; capacity_t is eligible CSD processing capacity.
## Observation contract and time boundaries
**Grain:** instruction × CSD × ISIN × intended settlement day × decision time. **Fields:** Public ESMA CSDR framework, synthetic ISIN liquidity/penalty groups, settlement instruction cutoff, fail reason and amendment history.. **Availability:** Penalty exclusions and rules must reflect versions legally in force before each instruction decision; ESMA technical advice is not automatically operative law..
Every input must carry `source_id, market, instrument_id, effective_at_utc, observed_at_utc, published_at_utc, available_at_utc, ingested_at_utc, immutable_revision_id, license_class`. Decision features may use only rows with `available_at_utc<=decision_at_utc`. Build synthetic examples when licensed data unavailable.
## Testable requirements
| ID | Requirement | Acceptance |
|---|---|---|
| REQ-001 | Form a legally feasible EU CSD securities settlement / securities finance return legs decision before action clock. | AC-001: reject stale/unknown/ineligible inputs |
| REQ-002 | Reconstruct `FIFO or largest-notional-first allowed settlement priority` with full cost and opportunity matching. | AC-002: deterministic fixture replicates baseline |
| REQ-003 | Reproduce `Constrained weighted-shortest-processing-time queue policy with eligibility rules` on frozen train and later holdout. | AC-003: no future features or post-selection |
| REQ-004 | Report `penalty liability, fail-days, priority-rule violations, operational throughput` with implementation loss. | AC-004: controlled uncertainty and capacity results |
| NFR-001 | Durable logs, lineage, source rights and reproducibility. | AC-005: positive/negative tests and locked versions |
| NFR-002 | No automatic trade, contract/legal interpretation or restricted disclosure. | AC-006: block unauthorized action |
## Hard no-go tests
**Confounding/leakage:** Misclassification of non-attributable fail causes or legal exclusion yields incorrect optimized queues.
**Falsification:** No statistically measurable improvement in held-out synthetic and later approved settlement scenarios under equal capacity.
**Production constraints:** Settlement bandwidth/available inventory and mandatory processing priority; adverse-penalty reallocations cannot violate service commitments.
**Economic scenario (not a forecast):** $145k hypothetical total 24-month labor/data/compute/compliance cost; rollout begins after 7 months; annual gross benefit scenarios $0k / $100k / $250k (downside/base/upside) for the remaining 1.4166666666666667 years. Net ROI=(benefit×active years−cost)/cost = -100.0% / -2.3% / 144.3%. These figures are scenario *assumptions*, not expected value, observed alpha, institutional revenue, or forward predictions.
## Non-goals
No confidential inputs, deployed strategy, compliance opinion, broker action or genuine 24-month ROI measurement is provided.
