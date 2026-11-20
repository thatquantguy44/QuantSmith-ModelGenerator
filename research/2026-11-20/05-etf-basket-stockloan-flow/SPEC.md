# SPEC — ETF Creation/Redemption Basket Shock to Stock-Loan Supply
**ID:** QMG-20261120-05 · **Category:** SECURITIES FINANCE · **Status:** DRAFT; empirical verification BLOCKED.
## Economic question and decision
An ETF primary-market basket can move specific equities and temporarily reshape lendable inventory and market demand independent of secondary price returns. Decision: Reserve lendable constituent supply ahead of known or forecasted ETF in-kind redemption/creation windows.
- **H1:** Point-in-time basket-flow measures predict incremental short-horizon available-to-lend changes beyond conventional index membership and short-interest proxies.
- **H0:** Hierarchical event study with issuer-basket aggregation and controls does not improve after-cost decision performance over Change in ETF shares outstanding plus index-event dummy.
## Formulation and constraints
```text
DeltaSupply_{i,t+h}=alpha_i+beta*BasketsDelta_{i,t}+gamma*Controls_{i,t}+epsilon
```
i is CUSIP, h forecast horizon, basket delta is an appropriately signed and actually available in-kind constituent-flow measure; no lookahead custom basket files.
## Observation contract and time boundaries
**Grain:** ETF × constituent × creation/redemption day × publication time. **Fields:** ETF disclosed holdings and creation units, public filings, official membership events, licensed AP basket/flows and loan availability for later study.. **Availability:** Only baskets available to a decision-maker before ETF order cutoff may be used; end-of-day holding reports are not morning baskets..
Every input must carry `source_id, market, instrument_id, effective_at_utc, observed_at_utc, published_at_utc, available_at_utc, ingested_at_utc, immutable_revision_id, license_class`. Decision features may use only rows with `available_at_utc<=decision_at_utc`. Build synthetic examples when licensed data unavailable.
## Testable requirements
| ID | Requirement | Acceptance |
|---|---|---|
| REQ-001 | Form a legally feasible US equity ETFs and underlying stock loan decision before action clock. | AC-001: reject stale/unknown/ineligible inputs |
| REQ-002 | Reconstruct `Change in ETF shares outstanding plus index-event dummy` with full cost and opportunity matching. | AC-002: deterministic fixture replicates baseline |
| REQ-003 | Reproduce `Hierarchical event study with issuer-basket aggregation and controls` on frozen train and later holdout. | AC-003: no future features or post-selection |
| REQ-004 | Report `inventory forecast MAE, short availability calibration, incremental net inventory carry, execution slippage` with implementation loss. | AC-004: controlled uncertainty and capacity results |
| NFR-001 | Durable logs, lineage, source rights and reproducibility. | AC-005: positive/negative tests and locked versions |
| NFR-002 | No automatic trade, contract/legal interpretation or restricted disclosure. | AC-006: block unauthorized action |
## Hard no-go tests
**Confounding/leakage:** Most executable AP basket details and actual stock-loan supply are not public.
**Falsification:** No incremental held-out inventory signal after availability alignment and underlying stock flow controls.
**Production constraints:** Inventory is limited by mandate, lendability and recalls; transaction fees and timing dominate thin basket effects.
**Economic scenario (not a forecast):** $190k hypothetical total 24-month labor/data/compute/compliance cost; rollout begins after 9 months; annual gross benefit scenarios $0k / $130k / $280k (downside/base/upside) for the remaining 1.25 years. Net ROI=(benefit×active years−cost)/cost = -100.0% / -14.5% / 84.2%. These figures are scenario *assumptions*, not expected value, observed alpha, institutional revenue, or forward predictions.
## Non-goals
No confidential inputs, deployed strategy, compliance opinion, broker action or genuine 24-month ROI measurement is provided.
