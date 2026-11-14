# EVALS — US–Euro Sovereign Curve Shock Decomposition with Data Vintages
**Status:** Design for tests, no experiment performed.

## Economic claim and comparator
- **H1:** Vintaged macro-announcement decomposition reduces out-of-sample cross-market duration hedge error versus rolling beta.
- **Comparator:** 60-day rolling DV01-neutral cross-market beta hedge..
- **Candidate:** Vintaged announcement factor model plus shrinkage hedge weights..
- **Advanced alternative:** Hierarchical structural yield-curve state-space with distinct real-rate and term-premium factor loading..
- **Metrics:** OOS hedging variance reduction, implementation shortfall, tail DV01 loss, signal turnover..
- **Stop/no-go:** Reject if hedge variance does not improve at least 5% net of turnover on independent event holdout.
- **Cost sensitivity:** USD $165k hypothetical 24-month engineering/data/maintenance cost; gross benefit sensitivity $0k–$355k over 24 months. Net ROI = (gross benefit − cost)/cost = **-100% to 115%**. NOT forecast or historical measurement. Economic lever: hypothetical $25m DV01-managed hedge sleeve with 0–120 bps equivalent annualized cost/risk improvement; not a backtest.

## Evaluation splits and safeguards
1. Set chronologically non-overlapping training, validation and holdout periods; embargo trades with outcome windows crossing splits.
2. Align all records to first permitted information availability, not economic reference date. end-of-release or next-session decision after releases disseminate; avoid falsely assuming instant access to revised series
3. Use exactly matched feasible opportunity sets and complete funding, execution, regulatory and operational frictions for baseline/candidate.
4. Compare against **no-action** when the cost of the position or data is not measurable.
5. Use time-blocked paired bootstrap uncertainty, relevant alternative market regimes and explicit multiple-hypothesis correction.
6. Test adverse implementation constraints: Restrict first pass to liquid Treasury/Bund futures and realistic FX basis and futures trading costs.
7. Stress identification risk: Public releases cannot recreate market consensus surprises without a licensed historical consensus dataset or explicit no-consensus baseline.
8. Record both gross and net metrics; a statistically significant signal is not necessarily profitable or operationally feasible.

## Specific negative/invariant tests
release timestamp in timezone; revised values versus first print; DV01 neutrality and FX translation.

## Shadow mode and production gate
AC-001–AC-005 need test evidence and reproducible run envelopes. No trading or execution without human risk and legal approval; where public proxies are insufficient, block P&L claims and publish only a risk-monitoring exploratory result. The accepted outcome may be **negative** and should remain in the research archive.
