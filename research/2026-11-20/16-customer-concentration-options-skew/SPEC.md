# SPEC — Issuer Customer-Concentration Disclosure to Earnings Options Skew
**ID:** QMG-20261120-16 · **Category:** DOMESTIC & GLOBAL MARKETS · **Status:** DRAFT; empirical verification BLOCKED.
## Economic question and decision
A large customer share can create correlated revenue jump exposure not captured by standard sector-level realized volatility. Decision: Hedge customer-loss jump risk in companies with concentrated customers using explicitly costed options structures.
- **H1:** Point-in-time EDGAR customer concentration disclosures explain forward options downside skew changes beyond leverage, size and event vol.
- **H0:** Censored-disclosure panel with inverse observation probability adjustment does not improve after-cost decision performance over Size/leverage/industry/earnings event-only option skew estimator.
## Formulation and constraints
```text
DownsideSkew_{i,t}=a+beta*CustomerHHI_{i,t-known}+gamma*EventControls_{i,t}+epsilon
```
HHI is sum of squared disclosed customer revenue shares (bounded/partially observed); t-known is filing dissemination time, not fiscal year end.
## Observation contract and time boundaries
**Grain:** issuer accepted filing × reported customer share × options quote timestamp. **Fields:** SEC EDGAR original issuer filings, customer concentration disclosures, single-stock option surface, earnings calendar, liquidity and corporate actions.. **Availability:** Use SEC acceptance timestamps and first published disclosure, not retroactive tagged XBRL after amended filings..
Every input must carry `source_id, market, instrument_id, effective_at_utc, observed_at_utc, published_at_utc, available_at_utc, ingested_at_utc, immutable_revision_id, license_class`. Decision features may use only rows with `available_at_utc<=decision_at_utc`. Build synthetic examples when licensed data unavailable.
## Testable requirements
| ID | Requirement | Acceptance |
|---|---|---|
| REQ-001 | Form a legally feasible US listed single-name equity options and SEC 10-K/10-Q issuers decision before action clock. | AC-001: reject stale/unknown/ineligible inputs |
| REQ-002 | Reconstruct `Size/leverage/industry/earnings event-only option skew estimator` with full cost and opportunity matching. | AC-002: deterministic fixture replicates baseline |
| REQ-003 | Reproduce `Censored-disclosure panel with inverse observation probability adjustment` on frozen train and later holdout. | AC-003: no future features or post-selection |
| REQ-004 | Report `post-filing skew residual, risk hedge efficiency, delta-neutral net performance and disclosure coverage` with implementation loss. | AC-004: controlled uncertainty and capacity results |
| NFR-001 | Durable logs, lineage, source rights and reproducibility. | AC-005: positive/negative tests and locked versions |
| NFR-002 | No automatic trade, contract/legal interpretation or restricted disclosure. | AC-006: block unauthorized action |
## Hard no-go tests
**Confounding/leakage:** Customer concentrations may be anonymized and nonrandomly omitted; options trade data can be illiquid.
**Falsification:** No post-filing incremental skew or hedge gain beyond conventional earnings-related jump risk.
**Production constraints:** Option open interest, bid/ask, assignment/maturity mechanics and volatile event hedging friction.
**Economic scenario (not a forecast):** $160k hypothetical total 24-month labor/data/compute/compliance cost; rollout begins after 9 months; annual gross benefit scenarios $0k / $85k / $260k (downside/base/upside) for the remaining 1.25 years. Net ROI=(benefit×active years−cost)/cost = -100.0% / -33.6% / 103.1%. These figures are scenario *assumptions*, not expected value, observed alpha, institutional revenue, or forward predictions.
## Non-goals
No confidential inputs, deployed strategy, compliance opinion, broker action or genuine 24-month ROI measurement is provided.
