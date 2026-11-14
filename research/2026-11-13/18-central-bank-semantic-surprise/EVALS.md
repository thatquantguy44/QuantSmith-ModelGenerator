# EVALS — Central-Bank Communication Semantic Surprise Across Languages
**Status:** Design for tests, no experiment performed.

## Economic claim and comparator
- **H1:** Claim-grounded semantic stance revisions add stable information beyond rate decision and scheduled policy surprise alone across languages.
- **Comparator:** Policy rate surprise (or no-surprise dummy without licensed expectation) and prior-day rate changes..
- **Candidate:** Source-grounded claim-difference extractor with multilingual uncertainty and simple linear evaluation..
- **Advanced alternative:** Constrained multilingual textual event state-space with calibration and abstention threshold..
- **Metrics:** out-of-sample price direction log loss, FX hedge information ratio, translation agreement and unsupported claim rate..
- **Stop/no-go:** Reject if no incremental holdout log-loss improvement or semantic extractor makes unsupported claims on challenge set.
- **Cost sensitivity:** USD $160k hypothetical 24-month engineering/data/maintenance cost; gross benefit sensitivity $0k–$320k over 24 months. Net ROI = (gross benefit − cost)/cost = **-100% to 100%**. NOT forecast or historical measurement. Economic lever: hypothetical $10m liquid G10 hedge sleeve with up to 160 bps 2-year value if statistically robust; zero benefit plausible.

## Evaluation splits and safeguards
1. Set chronologically non-overlapping training, validation and holdout periods; embargo trades with outcome windows crossing splits.
2. Align all records to first permitted information availability, not economic reference date. after official statement becomes public; never permit news articles, transcripts or price reactions from after decision in input
3. Use exactly matched feasible opportunity sets and complete funding, execution, regulatory and operational frictions for baseline/candidate.
4. Compare against **no-action** when the cost of the position or data is not measurable.
5. Use time-blocked paired bootstrap uncertainty, relevant alternative market regimes and explicit multiple-hypothesis correction.
6. Test adverse implementation constraints: Only next-session liquid FX/rates futures; policy event size, slippage and gap risk explicitly costed.
7. Stress identification risk: Translation distortions, backfilled statement updates, and post-event news leakage are especially severe for multilingual event models.
8. Record both gross and net metrics; a statistically significant signal is not necessarily profitable or operationally feasible.

## Specific negative/invariant tests
statement version hashes; input price cutoffs; language disagreement abstention; hallucination rejection.

## Shadow mode and production gate
AC-001–AC-005 need test evidence and reproducible run envelopes. No trading or execution without human risk and legal approval; where public proxies are insufficient, block P&L claims and publish only a risk-monitoring exploratory result. The accepted outcome may be **negative** and should remain in the research archive.
