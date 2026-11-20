# SPEC — Reg SHO Locate Evidence and Borrow-Capacity Audit Engine
**ID:** QMG-20261120-02 · **Category:** SECURITIES FINANCE · **Status:** DRAFT; empirical verification BLOCKED.
## Economic question and decision
A live quote, locate assurance and subsequent borrow fill are not interchangeable, and records may cross inconsistent clocks or quantities. Decision: Block or escalate a short-sale request if contemporaneous legally qualifying locate evidence or remaining documented quantity is insufficient.
- **H1:** Event-sourced evidence reconstruction detects noncompliant or capacity-exhausted locates earlier than end-of-day exception review without excess false rejects.
- **H0:** Typed event-sourcing finite-state verification with causal explainability does not improve after-cost decision performance over End-of-day deterministic locate exception SQL rules.
## Formulation and constraints
```text
min_policy c_FN*FN + c_FP*FP + c_D*Delay subject to permitted(request,t)<=documented_available_qty(t)
```
FN is an incorrectly accepted exception, FP an incorrectly blocked valid locate, and Delay is processing latency; all compliance rules require human-verified effective policy and exemptions.
## Observation contract and time boundaries
**Grain:** short-sale request × account × security × source × event timestamp. **Fields:** Synthetic short-sale order events, documented locate timestamps, source identity, shares remaining, exemptions and post-trade recalls; later private desk records only if approved.. **Availability:** Locate documentation and quantity must be timestamped before short sale; revised records cannot retroactively authorize prior orders..
Every input must carry `source_id, market, instrument_id, effective_at_utc, observed_at_utc, published_at_utc, available_at_utc, ingested_at_utc, immutable_revision_id, license_class`. Decision features may use only rows with `available_at_utc<=decision_at_utc`. Build synthetic examples when licensed data unavailable.
## Testable requirements
| ID | Requirement | Acceptance |
|---|---|---|
| REQ-001 | Form a legally feasible US equity securities lending and short-sale compliance decision before action clock. | AC-001: reject stale/unknown/ineligible inputs |
| REQ-002 | Reconstruct `End-of-day deterministic locate exception SQL rules` with full cost and opportunity matching. | AC-002: deterministic fixture replicates baseline |
| REQ-003 | Reproduce `Typed event-sourcing finite-state verification with causal explainability` on frozen train and later holdout. | AC-003: no future features or post-selection |
| REQ-004 | Report `prevented invalid requests, false blocks, recall error, audit completion time, p99 latency` with implementation loss. | AC-004: controlled uncertainty and capacity results |
| NFR-001 | Durable logs, lineage, source rights and reproducibility. | AC-005: positive/negative tests and locked versions |
| NFR-002 | No automatic trade, contract/legal interpretation or restricted disclosure. | AC-006: block unauthorized action |
## Hard no-go tests
**Confounding/leakage:** Reg SHO exemptions, broker responsibilities and settlement rules require qualified legal interpretation.
**Falsification:** Fails to flag intentionally missing/expired/overused locates on synthetic fixtures or blocks materially more valid trades than comparator.
**Production constraints:** Low per-request CPU; overhead per manual escalation and strict audit storage/retention authorization.
**Economic scenario (not a forecast):** $120k hypothetical total 24-month labor/data/compute/compliance cost; rollout begins after 6 months; annual gross benefit scenarios $0k / $115k / $200k (downside/base/upside) for the remaining 1.5 years. Net ROI=(benefit×active years−cost)/cost = -100.0% / 43.8% / 150.0%. These figures are scenario *assumptions*, not expected value, observed alpha, institutional revenue, or forward predictions.
## Non-goals
No confidential inputs, deployed strategy, compliance opinion, broker action or genuine 24-month ROI measurement is provided.
