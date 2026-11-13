# SOURCES — EM External-Funding Fragility via Currency Mismatch and IIP
**Source status:** official links/papers verified by live retrieval on November 13, 2026. No raw data was downloaded. An official URL never proves that the proposed trade-level series exists at the necessary cadence.

## 1. Free/open and published institutional starting points
- [BIS global liquidity indicator portal](https://data.bis.org/topics/GLI) — quarterly cross-border credit metrics and methodological notes.
- [IMF International Investment Position](https://data.imf.org/en/datasets/IMF.STA%3AIIP) — international investment positions; observe reporting lag and revision schedules.
- [Gabaix–Maggiori, International Liquidity and Exchange Rate Dynamics](https://doi.org/10.1093/qje/qjv016) — peer-reviewed FX capital flow theory, not validation of proposed signal.

**Suitability caveat:** BIS GLI and IMF IIP published quarterly with varying country coverage and revisions.

## 2. Licensed commercial data, only after contract and approval
FX forward executable quotes, sovereign CDS, emerging-market rate/liquidity curves.
Check access rights, research retention, reproducibility redistribution, index revisions, latency, data charges and instrument survivorship. Never upload licensed extracts to this public repository.

## 3. Permissioned/private data — strictly outside public GitHub/Slack
No required private data; broker risk limits optional and kept outside repo.
Treat any actual counterparty, position, customer, loan, account, RFQ or private quote as restricted.

## 4. Required data/temporal coverage
IMF IIP, BIS global liquidity quarterly FX credit, OECD macro where available, public reserve series and FX/sovereign returns. **Observation grain:** country × reporting quarter × first-public-availability time. **Decision horizon:** quarterly risk changes after actual statistical release; never refresh historic positions with today's revised values.
Each source row needs `available_at` measured by actual public release or authorized internal delivery, plus `effective_at` and revision-vintage tags.

## 5. Research literature
Any linked published paper is theory/benchmark context only. Its existence does NOT verify this idea, its ROI, alpha, data access or empirical success. Full literature and DOI coverage is **OPEN** for human research review.
