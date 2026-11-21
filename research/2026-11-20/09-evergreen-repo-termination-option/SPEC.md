# SPEC — Evergreen Repo Early-Termination Optionality Risk Budget
**ID:** QMG-20261120-09 · **Category:** SECURITIES FINANCE · **Status:** DRAFT; empirical verification BLOCKED.
## Economic question and decision
Contractual call/notice periods create embedded funding options not captured by standard fixed-maturity repo carry. Decision: Set rate/tenor risk charges for unilateral termination and extension rights in open repo or evergreen funding.
- **H1:** Notice-option-adjusted funding pricing reduces out-of-sample replacement-cost surprises versus duration-only term curve cost.
- **H0:** Least-squares Monte Carlo for bilateral asymmetric stop decisions does not improve after-cost decision performance over Static repo spread plus deterministic notice-day funding reserve.
## Formulation and constraints
```text
V_t=max(ExerciseValue_t, Carry_t+discount*E_t[V_{t+1}]) subject to NoticeDays,Eligibility
```
exercise and continuation are contract-party-specific; funder and borrower exercise incentives must be separately simulated.
## Observation contract and time boundaries
**Grain:** contract × notice period × funding day × interest-rate state. **Fields:** Synthetic open-repo terms, public SOFR and OFR repo curve history, legally enforceable reset/termination terms and funding costs.. **Availability:** Public repo rates have release lags; exact contract termination rights must be known at contract initiation, not retrofitted..
Every input must carry `source_id, market, instrument_id, effective_at_utc, observed_at_utc, published_at_utc, available_at_utc, ingested_at_utc, immutable_revision_id, license_class`. Decision features may use only rows with `available_at_utc<=decision_at_utc`. Build synthetic examples when licensed data unavailable.
## Testable requirements
| ID | Requirement | Acceptance |
|---|---|---|
| REQ-001 | Form a legally feasible Open and evergreen secured funding agreements decision before action clock. | AC-001: reject stale/unknown/ineligible inputs |
| REQ-002 | Reconstruct `Static repo spread plus deterministic notice-day funding reserve` with full cost and opportunity matching. | AC-002: deterministic fixture replicates baseline |
| REQ-003 | Reproduce `Least-squares Monte Carlo for bilateral asymmetric stop decisions` on frozen train and later holdout. | AC-003: no future features or post-selection |
| REQ-004 | Report `replacement funding loss, option premium calibration, cash-flow stress, tail liquidity gap` with implementation loss. | AC-004: controlled uncertainty and capacity results |
| NFR-001 | Durable logs, lineage, source rights and reproducibility. | AC-005: positive/negative tests and locked versions |
| NFR-002 | No automatic trade, contract/legal interpretation or restricted disclosure. | AC-006: block unauthorized action |
## Hard no-go tests
**Confounding/leakage:** Non-observed counterparty exercise behavior; public term repo alone does not identify proprietary notice clauses.
**Falsification:** Option charge unstable or no improvement over conservative notice reserve in stress holdouts.
**Production constraints:** Bilateral notice terms, term borrowing capacity, haircuts and closeout spreads constrain exercise decisions.
**Economic scenario (not a forecast):** $180k hypothetical total 24-month labor/data/compute/compliance cost; rollout begins after 10 months; annual gross benefit scenarios $0k / $105k / $270k (downside/base/upside) for the remaining 1.1666666666666667 years. Net ROI=(benefit×active years−cost)/cost = -100.0% / -31.9% / 75.0%. These figures are scenario *assumptions*, not expected value, observed alpha, institutional revenue, or forward predictions.
## Non-goals
No confidential inputs, deployed strategy, compliance opinion, broker action or genuine 24-month ROI measurement is provided.
