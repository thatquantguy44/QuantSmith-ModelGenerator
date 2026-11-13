# EVALS — EM External-Funding Fragility via Currency Mismatch and IIP
**Status:** Design for tests, no experiment performed.

## Economic claim and comparator
- **H1:** Release-vintage normalized foreign-currency credit-to-external-assets mismatch predicts EM stress windows beyond carry and spot volatility.
- **Comparator:** Traditional sovereign credit rating tier, FX carry and three-month realized volatility..
- **Candidate:** Point-in-time standardized funding mismatch factor with recession/regime interactions..
- **Advanced alternative:** Joint skewed macro-financial state-space with robust optimization and missing vintage uncertainty..
- **Metrics:** EM FX crash recall, max drawdown, FX-adjusted stress Brier, portfolio VaR breaches..
- **Stop/no-go:** Reject if stress recall or drawdown control fails to beat carry-vol baseline in holdout crises.
- **Cost sensitivity:** USD $125k hypothetical 24-month engineering/data/maintenance cost; gross benefit sensitivity $0k–$355k over 24 months. Net ROI = (gross benefit − cost)/cost = **-100% to 184%**. NOT forecast or historical measurement. Economic lever: hypothetical liquid $15m EM risk allocation where a small fraction of crash drawdown is avoided; no empirical hedge benefit.

## Evaluation splits and safeguards
1. Set chronologically non-overlapping training, validation and holdout periods; embargo trades with outcome windows crossing splits.
2. Align all records to first permitted information availability, not economic reference date. quarterly risk changes after actual statistical release; never refresh historic positions with today's revised values
3. Use exactly matched feasible opportunity sets and complete funding, execution, regulatory and operational frictions for baseline/candidate.
4. Compare against **no-action** when the cost of the position or data is not measurable.
5. Use time-blocked paired bootstrap uncertainty, relevant alternative market regimes and explicit multiple-hypothesis correction.
6. Test adverse implementation constraints: Use liquid EM FX forwards/ETFs only where available; include carry, forward points, market depth and capital controls.
7. Stress identification risk: Global liquidity metrics are quarterly; imputed weekly updates are model estimates, not observations.
8. Record both gross and net metrics; a statistically significant signal is not necessarily profitable or operationally feasible.

## Specific negative/invariant tests
vintage-aligned GDP denominators; reserve composition; sovereign survivorship; forward cost controls.

## Shadow mode and production gate
AC-001–AC-005 need test evidence and reproducible run envelopes. No trading or execution without human risk and legal approval; where public proxies are insufficient, block P&L claims and publish only a risk-monitoring exploratory result. The accepted outcome may be **negative** and should remain in the research archive.
