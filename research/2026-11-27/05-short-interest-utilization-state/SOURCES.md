# SOURCES — Short Interest versus Securities Loan Utilization State Decomposition
**QMG-20261127-05 | A — Securities finance | US exchange-listed equities | proposal only**
## 1. Public-first
- [FINRA API documentation](https://developer.finra.org/docs): Consolidated short interest dataset; documentation specifies availability by 4:40 p.m. ET on publication date. Respect actual release clock.
- [ESMA EU SFT market overview (9 April 2024)](https://www.esma.europa.eu/press-news/esma-news/esma-publishes-first-overview-eu-securities-financing-transactions-markets): Aggregate market context, not access to confidential trade repository rows.
Public entries verified on November 27, 2026, not evidence of granular data or legal redistribution. Required fields: reported SI, lender availability/utilization, corporate actions, lendable supply and fees. Release contract: ingest FINRA publication after 4:40 p.m. ET or later actual receipt; trade next eligible session. Use synthetic fixture if missing; mark actual-data evaluation BLOCKED. Do not use later corrections retroactively.
## 2. Licensed
licensed historical lendable supply and loan balances; verify entitlement, historical universe, quote executability, corporate actions and publication timing.
## 3. Permissioned/private
approved anonymized lending-event observations for state labels; keep outside public repository; no raw samples, identifiers or secrets. Paper searches remain pending except verified background items in source ledger. No external article proves the proposed hypothesis.
