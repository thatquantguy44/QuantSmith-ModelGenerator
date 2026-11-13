# SPEC — Central-Bank Communication Semantic Surprise Across Languages
**ID:** QMG-20261113-18 · **Status:** Draft; human approval required · **Category:** B · Domestic & global markets · **Geography:** US Federal Reserve, ECB and selected Asian monetary authorities

## Problem and decision
Translated central-bank statements can obscure a policy stance change; narrative models can also contaminate price signals with post-event commentary.
**Decision supported:** Quantify official policy-message *differences* between successive statements to adjust next-session FX/rates exposure.

## H1 versus H0
**H1:** Claim-grounded semantic stance revisions add stable information beyond rate decision and scheduled policy surprise alone across languages.
**H0:** A cost-inclusive Policy rate surprise (or no-surprise dummy without licensed expectation) and prior-day rate changes. matches or exceeds the candidate on strictly out-of-sample decisions. The intent is falsification, not confirmation.

## Mathematical problem and domain
```text
Surprise_t = SentenceDistance(text_t, text_(t-1)) - ExpectedShift_t; alpha_(t+1)=β*Surprise_t, with abstention on low translation confidence
```
text_t is official published statement as of event; ExpectedShift requires pre-event expectations and is omitted if unavailable rather than inferred ex post.
**Capacity and eligibility:** Only next-session liquid FX/rates futures; policy event size, slippage and gap risk explicitly costed.
Unspecified coefficients must be estimated only from training windows and no undocumented constraint may be relaxed.

## Source, clock and data contract
Versioned official policy statements; actual publication timestamps; pre-event interest rate futures; FX and rates price bars; translated text audit. **Observation grain:** central-bank event × original language × statement version × publication timestamp. **Decision horizon:** after official statement becomes public; never permit news articles, transcripts or price reactions from after decision in input.
At minimum require `observation_id`, `effective_at`, `published_at`, `available_at`, `ingested_at`, `source_uri`, `license_class`, `revision_id`, `unit`. `available_at <= decision_time` is mandatory for all market signals. New revisions create new records and must not silently overwrite historical decisions.

## Functional and nonfunctional requirements
| ID | Explicit requirement | Priority |
|---|---|---|
| REQ-001 | Model the permitted choice: Quantify official policy-message *differences* between successive statements to adjust next-session FX/rates exposure. | Must |
| REQ-002 | Reproduce feasible benchmark: Policy rate surprise (or no-surprise dummy without licensed expectation) and prior-day rate changes. | Must |
| REQ-003 | Implement candidate Source-grounded claim-difference extractor with multilingual uncertainty and simple linear evaluation. only after benchmark | Must |
| REQ-004 | Report out-of-sample price direction log loss, FX hedge information ratio, translation agreement and unsupported claim rate. and matched capacity/execution economics | Must |
| NFR-001 | Deterministic fixture replay, point-in-time lineage and seed/config pinning | Must |
| NFR-002 | Confidentiality, access/market eligibility, source licensing and manual review | Must |

## Acceptance criteria
| ID | Covers | Testable requirement |
|---|---|---|
| AC-001 | REQ-001,NFR-001 | Reject unavailable source vintages and impossible decision clocks |
| AC-002 | REQ-002 | Synthetic benchmark passes unit, cost and eligibility invariants |
| AC-003 | REQ-003 | Candidate uses same opportunities/cost rules; reproducible paired holdout |
| AC-004 | REQ-004 | Net economic metrics, intervals, sensitivity and capacity displayed |
| AC-005 | NFR-002 | Public output blocks private rows and unresolved authorization |

## Research economics
USD $160k hypothetical 24-month engineering/data/maintenance cost; gross benefit sensitivity $0k–$320k over 24 months. Net ROI = (gross benefit − cost)/cost = **-100% to 100%**. NOT forecast or historical measurement. Economic lever: hypothetical $10m liquid G10 hedge sleeve with up to 160 bps 2-year value if statistically robust; zero benefit plausible.. Source availability: Official statements are public, but original-language versions, vintage snapshots and proprietary market expectations may need archival work.
Funding, transaction cost and execution constraints require separate real calibration.

## Primary risks and negative gates
- **RISK-001:** Translation distortions, backfilled statement updates, and post-event news leakage are especially severe for multilingual event models.
- **RISK-002:** Data sparsity, nonstationarity, multiple testing and selection effects.
- **RISK-003:** Rights, settlement or investability restrictions may make an apparent opportunity infeasible.
- **Predeclared stop:** Reject if no incremental holdout log-loss improvement or semantic extractor makes unsupported claims on challenge set.
- **Non-goals:** Trading, legal/compliance approvals, publishing real P&L, or deployment from this spec alone.
