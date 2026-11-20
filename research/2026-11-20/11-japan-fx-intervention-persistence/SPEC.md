# SPEC — Japan FX Intervention Impact and Option-Skew Persistence
**ID:** QMG-20261120-11 · **Category:** DOMESTIC & GLOBAL MARKETS · **Status:** DRAFT; empirical verification BLOCKED.
## Economic question and decision
Official intervention disclosures arrive after execution; a hindsight backtest can misrepresent a trader's knowledge of actual intervention days. Decision: Determine when to reduce/hedge yen exposure following **publicly observed** intervention or subsequent official disclosure.
- **H1:** A release-time-corrected intervention-event measure predicts conditional 1–20-day FX variance/skew adjustment beyond macro announcements and momentum.
- **H0:** Disclosure-timestamp event study with matched controls and local projections does not improve after-cost decision performance over Standard spot momentum and monetary-policy announcement dummy.
## Formulation and constraints
```text
DeltaSkew_{t,h}=beta*InterventionKnownAt_t+gamma*MacroControls_t+epsilon_{t,h}
```
InterventionKnownAt_t is zero until event is publicly known or release issued; h is forward horizon, and skew is an executable options quote measure.
## Observation contract and time boundaries
**Grain:** intervention disclosure event × FX option tenor × quote timestamp. **Fields:** MOF monthly/quarterly intervention releases and dates, spot FX, short-term rate differential, timestamped USDJPY options/forward data.. **Availability:** MOF 2026 Q3 intervention details published Nov 9, 2026; never use ex-post intervention date labels in same-day live-time signals..
Every input must carry `source_id, market, instrument_id, effective_at_utc, observed_at_utc, published_at_utc, available_at_utc, ingested_at_utc, immutable_revision_id, license_class`. Decision features may use only rows with `available_at_utc<=decision_at_utc`. Build synthetic examples when licensed data unavailable.
## Testable requirements
| ID | Requirement | Acceptance |
|---|---|---|
| REQ-001 | Form a legally feasible Japan USD/JPY, yen crosses and FX options decision before action clock. | AC-001: reject stale/unknown/ineligible inputs |
| REQ-002 | Reconstruct `Standard spot momentum and monetary-policy announcement dummy` with full cost and opportunity matching. | AC-002: deterministic fixture replicates baseline |
| REQ-003 | Reproduce `Disclosure-timestamp event study with matched controls and local projections` on frozen train and later holdout. | AC-003: no future features or post-selection |
| REQ-004 | Report `incremental forward skew/vol forecast skill, delta-hedged net P&L, placebo events, risk-adjusted drawdown` with implementation loss. | AC-004: controlled uncertainty and capacity results |
| NFR-001 | Durable logs, lineage, source rights and reproducibility. | AC-005: positive/negative tests and locked versions |
| NFR-002 | No automatic trade, contract/legal interpretation or restricted disclosure. | AC-006: block unauthorized action |
## Hard no-go tests
**Confounding/leakage:** Actual intervention execution is not transparently known in real time; small event count undermines causal certainty.
**Falsification:** No differential response versus rate/central-bank news controls on withheld intervention disclosures or net-option-cost results.
**Production constraints:** Executable FX spot/options spreads, liquidity, event jump exposure, market access and derivatives capital.
**Economic scenario (not a forecast):** $180k hypothetical total 24-month labor/data/compute/compliance cost; rollout begins after 8 months; annual gross benefit scenarios $0k / $95k / $240k (downside/base/upside) for the remaining 1.3333333333333333 years. Net ROI=(benefit×active years−cost)/cost = -100.0% / -29.6% / 77.8%. These figures are scenario *assumptions*, not expected value, observed alpha, institutional revenue, or forward predictions.
## Non-goals
No confidential inputs, deployed strategy, compliance opinion, broker action or genuine 24-month ROI measurement is provided.
