# SPEC — SFTR Reporting Regime Drift and Public-Private Divergence Detector
**ID:** QMG-20261120-08 · **Category:** SECURITIES FINANCE · **Status:** DRAFT; empirical verification BLOCKED.
## Economic question and decision
Registry revisions and reporting practice changes can masquerade as repo/securities-lending market shifts. Decision: Detect structural reporting-quality breaks before using reported SFTR aggregates as market exposure signals.
- **H1:** Joint change-point tests on volumes, missingness and reported collateral taxonomy identify synthetic or historical reporting breaks more reliably than absolute-value outlier rules.
- **H0:** Robust multivariate Bayesian online change-point detection does not improve after-cost decision performance over Fixed ±3-sigma z-score alert on each series.
## Formulation and constraints
```text
Alarm_t=1{PosteriorP(change|feature_history)>q}; minimize detection_delay+lambda*false_alarms
```
q is alarm threshold chosen before holdout; changes attributed to reporting are hypotheses until repository audit.
## Observation contract and time boundaries
**Grain:** SFTR public aggregate series × jurisdiction × report vintage. **Fields:** ESMA reporting rules and publications, public aggregate exposures where available, historical methodology changes, synthetic backdated schema versions.. **Availability:** Use publication timestamps and repository versions, not reporting reference dates; detailed transaction data are supervisor-restricted..
Every input must carry `source_id, market, instrument_id, effective_at_utc, observed_at_utc, published_at_utc, available_at_utc, ingested_at_utc, immutable_revision_id, license_class`. Decision features may use only rows with `available_at_utc<=decision_at_utc`. Build synthetic examples when licensed data unavailable.
## Testable requirements
| ID | Requirement | Acceptance |
|---|---|---|
| REQ-001 | Form a legally feasible European securities financing transaction repositories decision before action clock. | AC-001: reject stale/unknown/ineligible inputs |
| REQ-002 | Reconstruct `Fixed ±3-sigma z-score alert on each series` with full cost and opportunity matching. | AC-002: deterministic fixture replicates baseline |
| REQ-003 | Reproduce `Robust multivariate Bayesian online change-point detection` on frozen train and later holdout. | AC-003: no future features or post-selection |
| REQ-004 | Report `break detection delay, false alarms, post-correction economic interpretation stability` with implementation loss. | AC-004: controlled uncertainty and capacity results |
| NFR-001 | Durable logs, lineage, source rights and reproducibility. | AC-005: positive/negative tests and locked versions |
| NFR-002 | No automatic trade, contract/legal interpretation or restricted disclosure. | AC-006: block unauthorized action |
## Hard no-go tests
**Confounding/leakage:** Only public aggregate data may be available, making root-cause verification incomplete.
**Falsification:** Synthetic change fixtures not detected within agreed delay or false alerts exceed preregistered burden.
**Production constraints:** Low runtime; review cost per alert and regulator/source availability dominate feasibility.
**Economic scenario (not a forecast):** $135k hypothetical total 24-month labor/data/compute/compliance cost; rollout begins after 6 months; annual gross benefit scenarios $0k / $90k / $190k (downside/base/upside) for the remaining 1.5 years. Net ROI=(benefit×active years−cost)/cost = -100.0% / 0.0% / 111.1%. These figures are scenario *assumptions*, not expected value, observed alpha, institutional revenue, or forward predictions.
## Non-goals
No confidential inputs, deployed strategy, compliance opinion, broker action or genuine 24-month ROI measurement is provided.
