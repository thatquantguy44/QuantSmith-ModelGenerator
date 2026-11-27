# Full Research Report — Batch 17 · November 23, 2026

**This is a research proposal, not evidence of trading returns or implementation.** Twenty complete falsifiable project briefs, 10 securities finance and 10 broad domestic/global markets. Scores and cost/benefit sensitivities are assumptions. Full interfaces and research artifacts live in individual folders.

## Ranked combined overview
| Rank | ID | Research idea | Priority/100 | Assumed base 24m net ROI | Focus |
|---:|---:|---|---:|---:|---|
| 1 | 01 | [Agency MBS Dollar-Roll Cheapest-to-Deliver Financing Option](./01-agency-mbs-dollar-roll-delivery-option/README.md) | 96 | 8.3% | A |
| 2 | 11 | [US Municipal Credit Vulnerability to Local Insurance Withdrawal](./11-us-muni-insurance-withdrawal-risk/README.md) | 95 | -11.5% | B |
| 3 | 02 | [Corporate Bond Securities Lending from CDS Basis Hedge Demand](./02-corporate-bond-cds-basis-borrow-demand/README.md) | 94 | 3.9% | A |
| 4 | 12 | [India Monsoon Surprise to Food CPI and Local Equity Pricing](./12-india-monsoon-cpi-equity-surprise/README.md) | 94 | -11.5% | B |
| 5 | 03 | [Repo Coupon and Principal Event Cash-Flow Netting Scheduler](./03-repo-coupon-cashflow-netting/README.md) | 93 | 25.3% | A |
| 6 | 13 | [European Interconnector Congestion Power-Spread State Estimator](./13-europe-power-congestion-spreads/README.md) | 93 | -14.8% | B |
| 7 | 04 | [Securities Loan Retroactive Rate Amendment Revenue Assurance](./04-stockloan-rate-amendment-auditor/README.md) | 92 | 50.8% | A |
| 8 | 14 | [Japanese Real-Estate Equity Cash-Flow Sensitivity to BOJ Rate Normalization](./14-japan-reit-rate-reset-cashflows/README.md) | 92 | -19.7% | B |
| 9 | 05 | [Borrow Scarcity Causal Effect on Equity Market-Maker Quoted Depth](./05-borrow-scarcity-equity-market-depth/README.md) | 91 | -31.8% | A |
| 10 | 15 | [Chile–Peru Copper Royalty Shock to Sovereign and Mining Credit](./15-latam-copper-royalty-credit/README.md) | 91 | -25.5% | B |
| 11 | 06 | [Securities Lending Cash Rebate Floor Optionality in Low-Rate Regimes](./06-lending-rebate-floor-optionalities/README.md) | 90 | -16.0% | A |
| 12 | 16 | [Biotech FDA Catalyst Probability versus Options Event Premium](./16-biotech-fda-event-variance-premium/README.md) | 90 | -29.5% | B |
| 13 | 07 | [Tri-Party Repo Margin Dispute Root-Cause and Evidence Classifier](./07-triparty-margin-dispute-root-cause/README.md) | 89 | 13.8% | A |
| 14 | 17 | [Sovereign DSA Rating Migration Event Pricing for Frontier Bonds](./17-frontier-dsa-rating-migration/README.md) | 89 | -39.3% | B |
| 15 | 08 | [Fed Standing Repo Facility as a Funding-Stress Option Exercise Signal](./08-fed-srf-funding-stress-option/README.md) | 88 | -3.6% | A |
| 16 | 18 | [US Bank Deposit Beta and Mark-to-Market Securities Run Risk](./18-us-bank-deposit-beta-run-risk/README.md) | 88 | 16.1% | B |
| 17 | 09 | [CCP Member Default Position-Porting Time and Liquidity Optimization](./09-ccp-member-porting-time-risk/README.md) | 87 | -47.2% | A |
| 18 | 19 | [OPEC Oil Balance Residuals and Refined Crack-Spread Transmission](./19-opec-oil-balance-crack-spread/README.md) | 87 | -4.2% | B |
| 19 | 10 | [Regulatory LCR/NSFR Shadow Cost of Secured Funding Collateral](./10-lcr-nsfr-secured-funding-shadow-price/README.md) | 86 | -11.1% | A |
| 20 | 20 | [Arbitrage-Free Equity Volatility Surface Repair Across Markets](./20-global-options-no-arbitrage-repair/README.md) | 86 | -24.3% | B |

### 01. Agency MBS Dollar-Roll Cheapest-to-Deliver Financing Option — 96/100 (Securities finance; United States / agency MBS TBA)
**Decision / economic problem:** Select TBA dollar-roll financing and permissible pool delivery sets versus holding specified pools financed through repo. TBA rolls embed delivery-option value; treating the drop as a pure financing rate may underprice pool selection and settlement frictions.

**Falsifiable H1:** Explicit deliverability and pool opportunity costs explain dollar-roll implied funding differences beyond coupon, term and simple financing spreads.

**Math (proposed):** `min_{q_p>=0} Σ_p q_p*(PoolCarry_p + DeliveryCost_p - RollDrop_p), subject to Σ_p q_p = DeliverableNotional, 0<=q_p<=PoolAvailable_p*Eligible_p`. **Variables/constraints:** q_p is eligible delivered pool notional, RollDrop is dollar-roll price drop, Eligible_p delivery eligibility; preserve coupon/payup units.

**Data + point-in-time:** TBA front/back prices, pools, payups, coupon schedules, specified-pool risk, MBSD netting, EPN eligibility and execution costs **Decision clock:** Decision at pre-roll executable quote; EPN pool assignment becomes known later and must not leak into earlier signals.

**Baseline:** Dollar-roll implied financing vs same-tenor generic repo without delivery-option valuation. **Initial model:** Constrained pool-delivery optimizer with observable pool financing carry and roll prices. **Advanced:** Stochastic pool quality and delivery-selection real-options game with cheapest-deliverable simulation.

**Metrics:** Net financing bps, cheapest-deliverable premium, pre-settlement fail exposure, netted capital and tail regret. **Falsification:** No stable out-of-sample cost-adjusted advantage over delivery-aware manual baseline at realistic pool eligibility.. **Threat:** Pool price selection, payup optionality, actual pool availability and post-trade EPN leakage..

**Execution/capacity:** Market depth and eligible pool inventory limit size; include bid/ask, delivery allocations, financing and clearing margin.. **Proposed tooling:** pandas, QuantLib, scipy.optimize, cvxpy. **Publication value:** High for delivery-option identification; economic calibration requires licensed pool execution data.

**Economic sensitivity:** $180k assumed total 24m development/data/maintenance cost; assumed launch in month 6; assumed annual gross outcome downside/base/upside $0k/$130k/$260k. Resulting 24m net ROI **-100.0% / 8.3% / 116.7% (downside/base/upside)**. These are invented transparent sensitivity inputs, not measured ROI, P&L, or investment advice.

**Public starting evidence:** [DTCC FICC Mortgage-Backed Securities Division](https://www.dtcc.com/products-and-services/clearing-settlement-services/fixed-income-clearing-corporation-ficc/mortgage-backed-securities-division); [DTCC Electronic Pool Notification](https://www.dtcc.com/clearing-and-settlement-services/ficc-mbsd/epn). **Paid need:** Executable TBA rolls, specified-pool prices, MBS prepayment factors. **Permissioned (never commit):** Approved pool inventory, counterparties and EPN allocations; never commit actual records. Status: proposal only; no empirical test, alpha finding or code.

### 02. Corporate Bond Securities Lending from CDS Basis Hedge Demand — 94/100 (Securities finance; US and European investment-grade / high-yield credit)
**Decision / economic problem:** Allocate bond lending supply to CDS-bond basis hedging demand with counterparty and liquidity limits. Bond loan fee and borrow utilization can rise when short-bond/long-CDS trades require physical inventory, but cash-bond liquidity masks causality.

**Falsifiable H1:** CDS-bond basis dislocations predict incremental observable bond borrowing demand after conditioning on issue float, liquidity and credit stress.

**Math (proposed):** `E[BorrowDemand_{i,t+1}|F_t]=f(Basis_{i,t},Float_i,Liquidity_{i,t}); max_q Σ_i q_i*(fee_i - failCost_i) with q_i≤available_i`. **Variables/constraints:** Basis=CDS spread minus matched cash-bond spread; q_i is feasible bond loan notional; borrower behavior must be estimated.

**Data + point-in-time:** CUSIP-level corporate bond lending fees/locates, CDS curves, TRACE trade activity, issue amount, corporate actions **Decision clock:** CDS and cash-bond spreads only after published executable quote times; lending fills observed subsequently.

**Baseline:** Trailing borrower request count and issue-size utilization. **Initial model:** Matched event study plus borrow-arrival hazard conditional on CDS-bond basis. **Advanced:** Structural joint CDS/bond market-maker inventory model with selection-corrected demand.

**Metrics:** Borrow-arrival log score, realized net fee improvement, stale quote rate and borrow supply capacity. **Falsification:** Estimated basis effects fail paired holdouts or increase rejected locates after slippage and liquidity controls.. **Threat:** Non-executable CDS quotes, bond TRACE delay and endogeneity of credit distress..

**Execution/capacity:** Bond borrow capacity and transaction costs can overwhelm narrow basis; never equate public volume with tradable borrow.. **Proposed tooling:** polars, statsmodels, lifelines, cvxpy. **Publication value:** High causal-market-microstructure potential; point-in-time supply is permissioned.

**Economic sensitivity:** $150k assumed total 24m development/data/maintenance cost; assumed launch in month 7; assumed annual gross outcome downside/base/upside $0k/$110k/$230k. Resulting 24m net ROI **-100.0% / 3.9% / 117.2% (downside/base/upside)**. These are invented transparent sensitivity inputs, not measured ROI, P&L, or investment advice.

**Public starting evidence:** [SEC EDGAR Data Access](https://www.sec.gov/search-filings/edgar-search-assistance/accessing-edgar-data); [New York Fed Primary Dealer Statistics](https://www.newyorkfed.org/markets/primarydealers.html). **Paid need:** Corporate bond TRACE histories, CDS quotes and bond lending locates. **Permissioned (never commit):** Permissioned borrower requests/loan data. Status: proposal only; no empirical test, alpha finding or code.

### 03. Repo Coupon and Principal Event Cash-Flow Netting Scheduler — 93/100 (Securities finance; US Treasuries, agencies and multi-currency repo)
**Decision / economic problem:** Minimize same-day cash deficits caused by collateral coupon/principal flows and contractual manufactured payments. Security cash-flow dates and bilateral payment terms can create avoidable gross cash movements even when net exposure is small.

**Falsifiable H1:** Event-aware legally permissible netting reduces liquidity buffer and operational exceptions versus cash-flow-independent settlement.

**Math (proposed):** `min_{f_{ij,t},B_t} Σ_t (c_B*B_t+c_F*|f_t|) s.t. Cash_t + B_t + inflow_t - outflow_t ≥0; NettingSet_{ij}=1`. **Variables/constraints:** f_ij,t are settlement payment flows; B_t is funding buffer; NettingSet is legal contractual binary.

**Data + point-in-time:** Public bond schedules, ex-coupon dates, settlement calendars, synthetic counterparties and netting agreements **Decision clock:** Coupon schedule published at issuance; adjustments and confirmed obligations only after contract notice timestamp.

**Baseline:** Gross independent payment processing with static buffer. **Initial model:** Mixed-integer liquidity scheduling with eligibility/netting-set constraints. **Advanced:** Stochastic event-flow MPC with missed payment penalties and legal-entity netting restrictions.

**Metrics:** Peak cash buffer, gross payment count, exception cost, settlement timeliness. **Falsification:** No capacity-adjusted cost reduction versus pre-netted conventional operations or violations of payment rights.. **Threat:** Wrong beneficial-ownership treatment, netting rights and special cash settlement terms..

**Execution/capacity:** Savings limited to payments legally eligible for netting; reconciliation costs, daylight overdraft fees and solver latency included.. **Proposed tooling:** ortools, cvxpy, networkx, pandas. **Publication value:** Medium operational OR result; deterministic synthetic audit is immediately feasible.

**Economic sensitivity:** $120k assumed total 24m development/data/maintenance cost; assumed launch in month 5; assumed annual gross outcome downside/base/upside $0k/$95k/$190k. Resulting 24m net ROI **-100.0% / 25.3% / 150.7% (downside/base/upside)**. These are invented transparent sensitivity inputs, not measured ROI, P&L, or investment advice.

**Public starting evidence:** [New York Fed Primary Dealer Statistics](https://www.newyorkfed.org/markets/primarydealers.html); [SEC EDGAR Data Access](https://www.sec.gov/search-filings/edgar-search-assistance/accessing-edgar-data). **Paid need:** Securities master coupon and settlement event feeds. **Permissioned (never commit):** Authorized repo contracts and cash-settlement messages. Status: proposal only; no empirical test, alpha finding or code.

### 04. Securities Loan Retroactive Rate Amendment Revenue Assurance — 92/100 (Securities finance; Global agent lending / US securities loans)
**Decision / economic problem:** Identify contractually unsupported retroactive fee amendments before invoice posting. Backdated fee changes, rate boundaries and returns can create avoidable invoice differences even without a pricing alpha.

**Falsifiable H1:** Bitemporal contract-and-loan event reconstruction detects more true billing exceptions than end-of-day price reconciliation without increasing false disputes.

**Math (proposed):** `Invoice_i=Σ_{d∈loanlife_i} Principal_{i,d} * Fee_{i,d} * DayFraction_d ; Error_i=Invoice_posted_i-Invoice_authorized_i`. **Variables/constraints:** Fee_i,d is effective authorized fee, distinct from late recorded amendment; Principal is open borrow notional.

**Data + point-in-time:** Synthetic loans, amendment lifecycle, dated fee notices, loan terminations, currency and day-count conventions **Decision clock:** Invoice run includes only fee amendments authorized and received before invoice cut-off, even if effective date is earlier.

**Baseline:** Latest agreed fee × end-period balance × elapsed days. **Initial model:** Bitemporal finite-state rate and loan lifecycle ledger with invariant checks. **Advanced:** Probabilistic anomaly prioritization atop an exact contract-aware billing engine.

**Metrics:** Synthetic exception precision/recall, manual hours, invoice basis-point leakage, false escalation rate. **Falsification:** No improvement in high-severity seeded exceptions relative to deterministic ledger, or unauthorized dispute actions.. **Threat:** Contract-level bilateral waiver rules, fee confirmation ambiguity and out-of-order event feeds..

**Execution/capacity:** Value in avoided losses and less manual rework, not trading alpha; false dispute costs and review minutes cap benefit.. **Proposed tooling:** duckdb, polars, pydantic, hypothesis. **Publication value:** Medium applied controls research with compelling falsifiable synthetic tests.

**Economic sensitivity:** $105k assumed total 24m development/data/maintenance cost; assumed launch in month 4; assumed annual gross outcome downside/base/upside $0k/$95k/$165k. Resulting 24m net ROI **-100.0% / 50.8% / 161.9% (downside/base/upside)**. These are invented transparent sensitivity inputs, not measured ROI, P&L, or investment advice.

**Public starting evidence:** [SEC EDGAR Data Access](https://www.sec.gov/search-filings/edgar-search-assistance/accessing-edgar-data); [BIS Basel III Monitoring Release, Sep 23 2026](https://www.bis.org/media-releases/20260923-basel-iii-risk-based-capital-and-leverage-ratios-are-stable-while-liquidity-indicators-show). **Paid need:** Commercial corporate actions, loan accounting system documentation. **Permissioned (never commit):** Loan confirmations, fee invoices, counterparty agreements under strict access. Status: proposal only; no empirical test, alpha finding or code.

### 05. Borrow Scarcity Causal Effect on Equity Market-Maker Quoted Depth — 91/100 (Securities finance; US equities and select developed markets)
**Decision / economic problem:** Adjust financing risk capital for equity liquidity provision when short-sale borrow becomes scarce. Borrow fee spikes coincide with volatility and funding stress; ordinary cross-sectional regressions confuse cause and effect.

**Falsifiable H1:** Exogenous changes to borrow supply lower subsequent displayed depth/increase effective spreads more than matched control stocks.

**Math (proposed):** `Depth_{i,t}=α_i+δ_t+β*BorrowSupplyShock_{i,t}+γ'X_{i,t}+ε_{i,t}; H0: β=0`. **Variables/constraints:** BorrowSupplyShock is preannounced/exogenous eligible inventory change; X contains liquidity and issuer controls.

**Data + point-in-time:** Borrow availability and fees, market quotes/trades, issuer event calendars and exclusion instruments **Decision clock:** Quote-decision timing after actual supply notice; event timestamps distinguish pre-event leak, regular session and close.

**Baseline:** Spread/depth forecasting using only realized volatility and market cap. **Initial model:** Matched differences-in-differences/event-time instrumental analysis. **Advanced:** Structural market-maker inventory equilibrium with dynamic borrowing constraint.

**Metrics:** Event-time β confidence interval, placebos, effective spread, depth and incremental risk price. **Falsification:** No pre-registered effect with valid pretrends/instruments or effect only on illiquid untradeable names.. **Threat:** Selection on distressed shorts, simultaneous volatility and hard-to-borrow endogenous events..

**Execution/capacity:** Not an unconditional trading signal; capacity depends on quote depth and borrow clearance, include adverse selection.. **Proposed tooling:** linearmodels, statsmodels, polars, econml. **Publication value:** High causal microstructure paper potential but costly identification.

**Economic sensitivity:** $220k assumed total 24m development/data/maintenance cost; assumed launch in month 9; assumed annual gross outcome downside/base/upside $0k/$120k/$310k. Resulting 24m net ROI **-100.0% / -31.8% / 76.1% (downside/base/upside)**. These are invented transparent sensitivity inputs, not measured ROI, P&L, or investment advice.

**Public starting evidence:** [SEC EDGAR Data Access](https://www.sec.gov/search-filings/edgar-search-assistance/accessing-edgar-data). **Paid need:** LOBSTER/order book or exchange TAQ and securities-lending locates. **Permissioned (never commit):** Authorized lending supply events and market-making decisions. Status: proposal only; no empirical test, alpha finding or code.

### 06. Securities Lending Cash Rebate Floor Optionality in Low-Rate Regimes — 90/100 (Securities finance; EUR, CHF, JPY and USD cash-collateralized securities lending)
**Decision / economic problem:** Price and hedge rebate-floor optionality embedded in cash-collateral loan agreements. Minimum rebate or fee floors make effective funding convex at negative short rates; a linear spread assumption can misstate value.

**Falsifiable H1:** Contract-aware nonlinear floor valuation reduces forecast carry error and improper pricing vs linear spread assumptions.

**Math (proposed):** `PV_floor=E^Q[Σ_t DF_t*CashCollateral_t*max(K-r_t,0)*Δt]; Revenue=baseFee+PV_floor-hedgeCost`. **Variables/constraints:** K is contractual rebate floor, r_t relevant overnight collateral rate, DF discount factor, Δt year fraction.

**Data + point-in-time:** Historical overnight benchmarks, collateral currency curves, cash balances, contract rebate-floor clauses **Decision clock:** Valuation at contract initiation using curve observed by quote cut-off, not future realized policy rates.

**Baseline:** Static contractual rebate minus benchmark with no optionality. **Initial model:** Rate-tree floor valuation and curve calibration with contract clause parser. **Advanced:** Multi-currency short-rate stochastic volatility and correlated collateral run-off scenario valuation.

**Metrics:** Pricing replication error, stress carry, calibration error and limit-breach count. **Falsification:** Valuation adds no meaningful incremental pricing accuracy to conservative quoted-fee schedules.. **Threat:** Floor rights and term structures vary by legal agreement; historic negative-rate regimes have sample limitations..

**Execution/capacity:** Profit only if floors contractually negotiated; hedge notional and floor illiquidity restrict scale.. **Proposed tooling:** QuantLib, scipy, pydantic, numpy. **Publication value:** High derivatives valuation link with direct legal contract boundary.

**Economic sensitivity:** $135k assumed total 24m development/data/maintenance cost; assumed launch in month 7; assumed annual gross outcome downside/base/upside $0k/$80k/$225k. Resulting 24m net ROI **-100.0% / -16.0% / 136.1% (downside/base/upside)**. These are invented transparent sensitivity inputs, not measured ROI, P&L, or investment advice.

**Public starting evidence:** [FRED Data Portal](https://fred.stlouisfed.org/); [Bank of Japan Time-Series Data Search](https://www.boj.or.jp/en/about/education/oshiete/statistics/h03.htm); [BIS Basel III Monitoring Release, Sep 23 2026](https://www.bis.org/media-releases/20260923-basel-iii-risk-based-capital-and-leverage-ratios-are-stable-while-liquidity-indicators-show). **Paid need:** OIS curves and vol surfaces with redistribution rights. **Permissioned (never commit):** Permissioned cash rebate agreements and collateral balances. Status: proposal only; no empirical test, alpha finding or code.

### 07. Tri-Party Repo Margin Dispute Root-Cause and Evidence Classifier — 89/100 (Securities finance; US and European tri-party collateral)
**Decision / economic problem:** Resolve margin disagreements by independently identifying stale marks, eligibility mismatches and cut-off conventions. Operational margin disputes are often triaged from unstructured tickets without reconstructing mark, haircut and event timing.

**Falsifiable H1:** A deterministic calculation engine plus provenance graph resolves more disputes correctly than keyword-based ticket routing.

**Math (proposed):** `DisputeAmount_j=Σ_i (Mark_{i,t}*(1-h_i)*Qty_i)_bank - Σ_i (Mark_{i,t}*(1-h_i)*Qty_i)_agent`. **Variables/constraints:** h_i haircut and Mark_i mark at contractual timestamp; compare sides only when valuation basis matches.

**Data + point-in-time:** Synthetic dispute notices, collateral marks, haircut schedules, legal clocks, status and resolution labels **Decision clock:** Use values known to both parties at agreed margin timestamp; never use later corrected marks to excuse earlier action.

**Baseline:** FIFO triage by dispute amount and ticket keywords. **Initial model:** Deterministic valuation reconciliation then provenance-based root-cause ranking. **Advanced:** Constrained language-model document extraction with deterministic verifier and abstain-on-conflict.

**Metrics:** Seeded root-cause accuracy, false escalations, time-to-resolution, unresolved material exposure. **Falsification:** LLM cannot improve verified resolver without hallucinated legal clauses or unacceptable false settlements.. **Threat:** Conflicting vendor marks, jurisdiction-specific terms, privacy and LLM overconfidence..

**Execution/capacity:** Operational capacity limited by manual reviewer; never auto-settle margin on agent output.. **Proposed tooling:** pydantic, polars, networkx, spaCy, pytest. **Publication value:** Medium-high trustworthy AI plus deterministic risk operations.

**Economic sensitivity:** $145k assumed total 24m development/data/maintenance cost; assumed launch in month 6; assumed annual gross outcome downside/base/upside $0k/$110k/$205k. Resulting 24m net ROI **-100.0% / 13.8% / 112.1% (downside/base/upside)**. These are invented transparent sensitivity inputs, not measured ROI, P&L, or investment advice.

**Public starting evidence:** [OFR US Repo Markets Data Release](https://www.financialresearch.gov/short-term-funding-monitor/datasets/repo/); [BIS Basel III Monitoring Release, Sep 23 2026](https://www.bis.org/media-releases/20260923-basel-iii-risk-based-capital-and-leverage-ratios-are-stable-while-liquidity-indicators-show). **Paid need:** Tri-party margin conventions and licensed independent pricing feeds. **Permissioned (never commit):** Authorized CSA, marks, margin tickets and legal evidence. Status: proposal only; no empirical test, alpha finding or code.

### 08. Fed Standing Repo Facility as a Funding-Stress Option Exercise Signal — 88/100 (Securities finance; US overnight secured funding)
**Decision / economic problem:** Monitor time-lagged facility usage and infer when broad repo funding stress warrants buffer review. SRF usage can be distorted by auction mechanics and participants' idiosyncratic conditions, not just aggregate funding scarcity.

**Falsifiable H1:** Publication-aligned SRF utilization and awarded-rate dispersion improve next-session funding stress classification beyond SOFR-GC spread alone.

**Math (proposed):** `P(Stress_{t+1}=1|F_t)=logit^{-1}(β0+β1*SRFAward_t+β2*RateDisp_t+β3*SOFRSpread_t)`. **Variables/constraints:** Stress is pre-defined funding event; F_t contains only SRF summary published by decision time.

**Data + point-in-time:** Official SRF accepted/submitted quantities, summary rates, SOFR, OFR cleared/triparty repo aggregates **Decision clock:** Use posted operation result time and repo series 1-2-day publication lags; do not use same-day hidden participant-level bids.

**Baseline:** SOFR-GC spread threshold with no SRF information. **Initial model:** Event-conditioned calibrated logistic hazard with lag-safe publication ledger. **Advanced:** Structural real-option exercise mapping latent facility usage and dealer cash constraints.

**Metrics:** Brier score, AUPRC, stress false alarm, lead-time, calibrated probability. **Falsification:** No holdout information gain after timing correction, or false positives overwhelm funding buffer costs.. **Threat:** SRF operational parameter changes, known policy regime shifts, lack of entity-level same-day data..

**Execution/capacity:** Research output is risk-monitoring, not direct trading opportunity; facility eligibility and costs differ by participant.. **Proposed tooling:** statsmodels, sklearn, polars, pydantic. **Publication value:** Medium credible public funding-stress methodology; avoid claimed real-time detection.

**Economic sensitivity:** $115k assumed total 24m development/data/maintenance cost; assumed launch in month 5; assumed annual gross outcome downside/base/upside $0k/$70k/$170k. Resulting 24m net ROI **-100.0% / -3.6% / 134.1% (downside/base/upside)**. These are invented transparent sensitivity inputs, not measured ROI, P&L, or investment advice.

**Public starting evidence:** [NY Fed Standing Repo Facility FAQ](https://www.newyorkfed.org/markets/repo-agreement-ops-faq-241218); [OFR US Repo Markets Data Release](https://www.financialresearch.gov/short-term-funding-monitor/datasets/repo/); [New York Fed Primary Dealer Statistics](https://www.newyorkfed.org/markets/primarydealers.html). **Paid need:** Intraday secured-funding quotations and market depth. **Permissioned (never commit):** Permissioned liquidity buffers/cash funding obligations for downstream assessment. Status: proposal only; no empirical test, alpha finding or code.

### 09. CCP Member Default Position-Porting Time and Liquidity Optimization — 87/100 (Securities finance; Global cleared rates and repo portfolios)
**Decision / economic problem:** Choose contingent porting routes and liquidity reserves for a hypothetical clearing-member default. Porting eligible positions can fail due to margin deadlines, client permissions and receiving-member constraints even with adequate default-fund assets.

**Falsifiable H1:** A capacity-constrained porting algorithm lowers simulated liquidation shortfall and time-to-restore relative to static member choice.

**Math (proposed):** `min_{x_{ij}} Σ_{ij} x_{ij}*(PortDelay_{ij}+λ*MarginShortfall_{ij}) subject to Σ_j x_{ij}≤Position_i, K_j≥Σ_i x_{ij}`. **Variables/constraints:** x_ij assigned position notional, K_j receiving-member capacity; only eligible clients/contracts included.

**Data + point-in-time:** Public CCP rulebooks; synthetic position/eligibility and margin profiles; simulated member outage **Decision clock:** Use rule versions effective on default scenario date, exclude assumptions from later CCP notices.

**Baseline:** Manual first-available eligible clearing member routing. **Initial model:** Multi-period mixed-integer stochastic porting/survival flow simulator. **Advanced:** Distributionally robust queueing network with correlated member liquidity and stress haircuts.

**Metrics:** Porting completion by deadline, unmet margin, loss given port failure, rerouting overhead. **Falsification:** No improvement in adverse default scenarios over conservative porting alternatives or reliance on forbidden client position data.. **Threat:** Actual CCP porting legality and bilateral customer consents unknown, correlated failures may be unidentifiable..

**Execution/capacity:** Not a deployable CCP recovery plan; scenario policy must be vetted by legal and risk.. **Proposed tooling:** ortools, simpy, scipy, networkx. **Publication value:** High OR under recovery constraints, empirical porting evidence likely sparse.

**Economic sensitivity:** $210k assumed total 24m development/data/maintenance cost; assumed launch in month 10; assumed annual gross outcome downside/base/upside $0k/$95k/$330k. Resulting 24m net ROI **-100.0% / -47.2% / 83.3% (downside/base/upside)**. These are invented transparent sensitivity inputs, not measured ROI, P&L, or investment advice.

**Public starting evidence:** [DTCC FICC Mortgage-Backed Securities Division](https://www.dtcc.com/products-and-services/clearing-settlement-services/fixed-income-clearing-corporation-ficc/mortgage-backed-securities-division); [BIS Basel III Monitoring Release, Sep 23 2026](https://www.bis.org/media-releases/20260923-basel-iii-risk-based-capital-and-leverage-ratios-are-stable-while-liquidity-indicators-show). **Paid need:** Clearing member cost/risk reference agreements. **Permissioned (never commit):** Strictly permissioned client margin/porting agreements. Status: proposal only; no empirical test, alpha finding or code.

### 10. Regulatory LCR/NSFR Shadow Cost of Secured Funding Collateral — 86/100 (Securities finance; Global banks; US/EU Basel liquidity reporting frameworks)
**Decision / economic problem:** Allocate financing transactions by incremental liquidity-ratio headroom consumption, not only nominal repo spread. A cheap repo can be uneconomic when it reduces HQLA or increases required stable funding disproportionately.

**Falsifiable H1:** Dual-priced LCR/NSFR constraints reorder feasible funding selections and improve all-in liquidity-adjusted economics versus spread ranking.

**Math (proposed):** `min_x Σ_i (r_i*x_i + k_i*x_i) subject to HQLA(x)/NetCashOutflows(x)≥LCR_min and ASF(x)/RSF(x)≥NSFR_min, Σ_i x_i≥Need`. **Variables/constraints:** x_i secured funding quantities, k_i legal balance-sheet charge; LCR, ASF, RSF use approved regulatory definitions.

**Data + point-in-time:** Public Basel ratio methodology/aggregate trends, synthetic collateral classes, cashflow ladder and legal-entity matrices **Decision clock:** Regulatory rule version, haircut classification and reporting entity apply as of funding decision.

**Baseline:** Rank repo offers by quoted rate subject to gross notional limits. **Initial model:** Linear/mixed-integer secured funding allocation with LCR/NSFR dual-price attribution. **Advanced:** Scenario-based shadow-price frontier with intraday and quarter-end liquidity risk.

**Metrics:** All-in liquidity-adjusted cost, marginal dual price, buffer breaches, sensitivity to rule version. **Falsification:** No cost difference over conservative liquidity-constrained benchmark or unstable/uninterpretable duals.. **Threat:** Entity-specific regulatory implementation and internal forecasts differ; cannot reconstruct actual LCR from public totals..

**Execution/capacity:** Use only approved internal regulatory measures when available; funding choices constrained by entity/collateral eligibility.. **Proposed tooling:** cvxpy, pyomo, scipy, pydantic. **Publication value:** High applied Basel economics; data rights and entity-specific interpretation constrain proof.

**Economic sensitivity:** $180k assumed total 24m development/data/maintenance cost; assumed launch in month 8; assumed annual gross outcome downside/base/upside $0k/$120k/$280k. Resulting 24m net ROI **-100.0% / -11.1% / 107.4% (downside/base/upside)**. These are invented transparent sensitivity inputs, not measured ROI, P&L, or investment advice.

**Public starting evidence:** [BIS Basel III Monitoring Release, Sep 23 2026](https://www.bis.org/media-releases/20260923-basel-iii-risk-based-capital-and-leverage-ratios-are-stable-while-liquidity-indicators-show); [OFR US Repo Markets Data Release](https://www.financialresearch.gov/short-term-funding-monitor/datasets/repo/). **Paid need:** Executable secured funding curves and legal category taxonomies. **Permissioned (never commit):** Bank-specific eligible HQLA, ASF/RSF and regulatory reporting data. Status: proposal only; no empirical test, alpha finding or code.

### 11. US Municipal Credit Vulnerability to Local Insurance Withdrawal — 95/100 (Global/domestic quant research; United States coastal, wildfire and flood-exposed municipal issuers)
**Decision / economic problem:** Prioritize municipal-credit surveillance and pricing by property tax base sensitivity to insurance availability. Tax-base deterioration from insurance affordability may be a forward municipal credit risk not captured by standard debt ratios.

**Falsifiable H1:** Hazard exposure × insurance withdrawal proxies predict later tax-roll stress/spread changes beyond debt-service coverage and demographics.

**Math (proposed):** `ΔCreditSpread_{c,t+h}=β*(Hazard_c×InsuranceShock_{c,t})+γ'X_{c,t}+μ_c+τ_t+ε`. **Variables/constraints:** c is issuer county/service area, h forward horizon; InsuranceShock uses published insurer exit/premium information.

**Data + point-in-time:** County FEMA risk, EMMA issuer disclosures, municipal price quotes, property valuations, insurer exit/public rate filings **Decision clock:** County/issuer boundary vintage and disclosure posting timestamp; FEMA risk version frozen at decision date.

**Baseline:** Debt-to-revenue and issuer-rating-only spread screen. **Initial model:** Geospatial panel DiD with insurance availability shock and issuer boundary crosswalk. **Advanced:** Graph exposure propagation into municipal tax receipts with heterogeneous hazard risk.

**Metrics:** Out-of-sample spread rank IC, change in tax revenue, false alerts, distress recall. **Falsification:** No incremental out-of-time predictive effect after socioeconomic covariates and issuer-selection controls.. **Threat:** FEMA risk baseline old; climate model not equivalent to observed insurance withdrawal; selective municipal disclosure..

**Execution/capacity:** Muni bonds illiquid, spread carry/horizon may exceed signal; favor risk-monitoring before trading.. **Proposed tooling:** geopandas, statsmodels, duckdb, linearmodels. **Publication value:** High public-policy credit research, data linkage and causal design substantial.

**Economic sensitivity:** $160k assumed total 24m development/data/maintenance cost; assumed launch in month 7; assumed annual gross outcome downside/base/upside $0k/$100k/$260k. Resulting 24m net ROI **-100.0% / -11.5% / 130.2% (downside/base/upside)**. These are invented transparent sensitivity inputs, not measured ROI, P&L, or investment advice.

**Public starting evidence:** [FEMA National Risk Index public catalog](https://catalog.data.gov/dataset/national-risk-index-nri-data); [MSRB EMMA Continuing Disclosures](https://www.msrb.org/Continuing-Disclosure). **Paid need:** Muni TRACE-like transaction data, catastrophe insurer premium/rate datasets. **Permissioned (never commit):** Authorized portfolio holdings and issuer due diligence only. Status: proposal only; no empirical test, alpha finding or code.

### 12. India Monsoon Surprise to Food CPI and Local Equity Pricing — 94/100 (Global/domestic quant research; India, state agriculture, INR and Indian listed consumer equities)
**Decision / economic problem:** Time/hedge exposures to monsoon-sensitive consumption and agriculture pricing after publicly available rainfall surprises. Calendar-average monsoon anomalies conceal crop-area heterogeneity and staggered CPI market dissemination.

**Falsifiable H1:** Rainfall surprises weighted by district crop patterns predict food-CPI subcomponents and cross-sectional consumer equity earnings revisions beyond national rainfall.

**Math (proposed):** `Shock_t=Σ_d CropWeight_d*(Rain_d,t - Normal_d,t); ΔCPI_{t+h}=α+β*Shock_t+γ'Controls_t+ε`. **Variables/constraints:** d district; crop weights fixed pre-season; h forecast horizon; normals from training vintage.

**Data + point-in-time:** IMD daily district rain, crop sowing weights, RBI CPI release, state-level harvest, NSE sector returns **Decision clock:** IMD publication timestamp and next-tradable-session; CPI only after official release, no revisions used retroactively.

**Baseline:** All-India seasonal rainfall deviation plus autoregressive food CPI. **Initial model:** Hierarchical spatial distributed-lag regression + causal crop weighting. **Advanced:** Weather-to-crop graph structural state-space model with uncertainty propagation.

**Metrics:** CPI MAE, sector neutral-return IC, hit rate net costs, seasonal robustness. **Falsification:** No incremental holdout inflation forecast or stock-return effect against rainfall benchmark.. **Threat:** Historical IMD OGD resources lag, crop mix revisions, rainfall not yield and policy interventions..

**Execution/capacity:** Large liquid Indian stocks capacity feasible only with correct foreign-investor access, FX costs and exchange calendars.. **Proposed tooling:** xarray, geopandas, pymc, statsmodels. **Publication value:** High global macro/physical data causal contribution if geographic data quality clears.

**Economic sensitivity:** $160k assumed total 24m development/data/maintenance cost; assumed launch in month 7; assumed annual gross outcome downside/base/upside $0k/$100k/$240k. Resulting 24m net ROI **-100.0% / -11.5% / 112.5% (downside/base/upside)**. These are invented transparent sensitivity inputs, not measured ROI, P&L, or investment advice.

**Public starting evidence:** [India Meteorological Department Rainfall Information](https://mausam.imd.gov.in/responsive/rainfallinformation.php); [India OGD Rainfall History](https://data.gov.in/catalog/rainfall-india). **Paid need:** Historical NSE returns and detailed CPI release vintages. **Permissioned (never commit):** Authorized investment eligibility and broker execution curves. Status: proposal only; no empirical test, alpha finding or code.

### 13. European Interconnector Congestion Power-Spread State Estimator — 93/100 (Global/domestic quant research; France, Germany, Benelux, Nordic and Iberian bidding zones)
**Decision / economic problem:** Select hedged cross-zone power spread exposures conditional on public transfer constraints. Observed day-ahead power spread contains congestion rents, bidding-zone rules and renewable shocks; unconstrained price regressions overstate arbitrage.

**Falsifiable H1:** Transmission-capacity-corrected congestion states improve next-day risk classification and hedge calibration versus load-only spread models.

**Math (proposed):** `Spread_{a,b,t}=Price_a,t-Price_b,t; Flow_{ab,t}≤ATC_{ab,t}; max_q E[q*Spread-CongestionCost(q)] with |q|≤AccessCap`. **Variables/constraints:** a,b bidding zones; ATC available transfer capacity; q a hypothetical permitted hedge, not a physically available arbitrage.

**Data + point-in-time:** ENTSO-E day-ahead prices, transfer capacities, interconnector outages, wind/load forecasts and contract liquidity **Decision clock:** Only ENTSO-E forecasts published before day-ahead bidding deadline; actual flows/prices are evaluation targets.

**Baseline:** Historical seasonal hourly spread by zone pair. **Initial model:** Physical-congestion regime HMM with capacity-constrained exposure mapper. **Advanced:** Stochastic DC power flow and multi-region graph forecasts with out-of-area transfer shadow prices.

**Metrics:** Congestion regime Brier score, spread MAE, feasible net hedge carry and stress CVaR. **Falsification:** Spread gains disappear after simultaneous public forecast access, congestion settlement and capacity rights.. **Threat:** Cross-zone transmission rights and operational capacities not freely tradable; timestamps and price revisions..

**Execution/capacity:** Transmission rights/market access and collateral requirements dominate quoted spread opportunities.. **Proposed tooling:** pypsa, xarray, statsmodels, cvxpy. **Publication value:** Very high physics/market design; data-rights and operational access are gating.

**Economic sensitivity:** $220k assumed total 24m development/data/maintenance cost; assumed launch in month 9; assumed annual gross outcome downside/base/upside $0k/$150k/$355k. Resulting 24m net ROI **-100.0% / -14.8% / 101.7% (downside/base/upside)**. These are invented transparent sensitivity inputs, not measured ROI, P&L, or investment advice.

**Public starting evidence:** [ENTSO-E Transparency Platform File Library Guide, Oct 9 2026](https://transparencyplatform.zendesk.com/hc/en-us/articles/35960137882129-File-Library-Guide); [US EIA Public API](https://www.eia.gov/opendata/v1/). **Paid need:** Executable EPEX/ICE forward curves and interconnector rights prices. **Permissioned (never commit):** Permissioned utility node positions and hedging restrictions. Status: proposal only; no empirical test, alpha finding or code.

### 14. Japanese Real-Estate Equity Cash-Flow Sensitivity to BOJ Rate Normalization — 92/100 (Global/domestic quant research; Japan J-REITs and commercial real estate)
**Decision / economic problem:** Distinguish J-REIT rate-reset liability timing and property yield spreads rather than duration-only price sensitivity. Nominal Japanese policy changes transmit unevenly to fixed versus floating J-REIT liabilities and rental pass-through.

**Falsifiable H1:** Public debt-maturity reset exposure explains post-policy J-REIT return dispersion beyond NAV discount and generic duration beta.

**Math (proposed):** `CashInterest_{i,t+h}=Σ_m Debt_{i,m}*(Coupon_{i,m}+ResetBeta_{i,m}*ΔRate_t); ΔAFFO_i≈-ΔCashInterest_i+RentPassThrough_i`. **Variables/constraints:** i REIT, m debt tranche, ResetBeta contractual floating/reset sensitivity; AFFO cash flow.

**Data + point-in-time:** BOJ rate time series, J-REIT bond/debt disclosures, rent index, total returns and market-based NAV **Decision clock:** Use release/filing acceptance before BOJ event and timestamp debt disclosure versions.

**Baseline:** Market REIT index duration and price-to-NAV score. **Initial model:** Disclosure-derived maturity-wall factor with event-based hedged return regressions. **Advanced:** Tenant lease rollover and financing reset structural cash-flow model.

**Metrics:** AFFO forecast error, sector-neutral return IC, liquidity-adjusted drawdown, event placebo. **Falsification:** No incremental post-rate-shift forecast after issuer fixed-effects and NAV-duration controls.. **Threat:** Japanese disclosure translation/lease renewal timing and selective REIT survivorship..

**Execution/capacity:** J-REIT constituent liquidity, FX hedge and foreign-investor restrictions limit realized capacity.. **Proposed tooling:** pandas, polars, statsmodels, pydantic. **Publication value:** Medium-high Japan rates/property cross-asset insight, bilingual source QC.

**Economic sensitivity:** $150k assumed total 24m development/data/maintenance cost; assumed launch in month 7; assumed annual gross outcome downside/base/upside $0k/$85k/$235k. Resulting 24m net ROI **-100.0% / -19.7% / 121.9% (downside/base/upside)**. These are invented transparent sensitivity inputs, not measured ROI, P&L, or investment advice.

**Public starting evidence:** [Bank of Japan Time-Series Data Search](https://www.boj.or.jp/en/about/education/oshiete/statistics/h03.htm); [SEC EDGAR Data Access](https://www.sec.gov/search-filings/edgar-search-assistance/accessing-edgar-data). **Paid need:** TSE J-REIT historical prices and Japanese property rent indices. **Permissioned (never commit):** Approved real estate securities trade cost estimates. Status: proposal only; no empirical test, alpha finding or code.

### 15. Chile–Peru Copper Royalty Shock to Sovereign and Mining Credit — 91/100 (Global/domestic quant research; Chile and Peru, mining and sovereign USD/local-currency credit)
**Decision / economic problem:** Hedge commodity-linked fiscal and issuer credit risk around public mining tax and royalty changes. Copper price explains broad earnings but fiscal royalty changes can shift tax take and mine investment with different lags.

**Falsifiable H1:** Legislated effective marginal royalty changes predict issuer-versus-sovereign credit spread dispersion beyond copper returns.

**Math (proposed):** `ΔSpread_{i,t+h}=β*Exposure_i*ΔRoyaltyRate_t+θ*ΔCopperPrice_t+γ'X_i,t+ε`. **Variables/constraints:** Exposure_i public geographic mine revenue, ΔRoyaltyRate legislated effective tax not mere bill proposal.

**Data + point-in-time:** USGS production, government royalty statutes, country budgets, company annual filings, credit spreads and currency **Decision clock:** Policy event recognized at official publication/enactment time; annual USGS data only upon issuance.

**Baseline:** Copper price beta plus sovereign spread changes. **Initial model:** Event study with cross-sectional mine exposure and staggered law timing. **Advanced:** Partial equilibrium mine-option tax model under investment deferral and country sovereign budget feedback.

**Metrics:** Event abnormal spread, FX-adjusted carry, political timing placebo, credit risk attribution. **Falsification:** No holdout effect after commodity beta and country shock controls or cannot identify legal effective date.. **Threat:** Anticipatory legislative pricing, issuer/sov high correlations, illiquid local bond prices..

**Execution/capacity:** Bid/ask for mining credits and FX may swamp basis; avoid assuming continuous trading around policy announcements.. **Proposed tooling:** statsmodels, linearmodels, pandas, scipy. **Publication value:** High international policy event identification, legal timing difficult.

**Economic sensitivity:** $170k assumed total 24m development/data/maintenance cost; assumed launch in month 8; assumed annual gross outcome downside/base/upside $0k/$95k/$260k. Resulting 24m net ROI **-100.0% / -25.5% / 103.9% (downside/base/upside)**. These are invented transparent sensitivity inputs, not measured ROI, P&L, or investment advice.

**Public starting evidence:** [USGS Mineral Commodity Summaries 2026 dataset](https://www.usgs.gov/data/mineral-commodity-summaries-2026-data-release); [SEC EDGAR Data Access](https://www.sec.gov/search-filings/edgar-search-assistance/accessing-edgar-data). **Paid need:** LATAM sovereign CDS, mining corporate bond and local FX data. **Permissioned (never commit):** Authorized portfolio issuer due diligence only. Status: proposal only; no empirical test, alpha finding or code.

### 16. Biotech FDA Catalyst Probability versus Options Event Premium — 90/100 (Global/domestic quant research; US small/mid-cap biotech equity and listed options)
**Decision / economic problem:** Test whether equity option implied event moves overstate conditional post-decision realized jumps at fixed risk limits. Catalyst calendars are susceptible to hindsight because FDA decision timing, clinical surprises and halted quotes interact.

**Falsifiable H1:** Official pre-event regulatory state improves risk-adjusted event-volatility pricing relative to a generic historical event move.

**Math (proposed):** `ExpectedJumpVar_i=Σ_s p_{i,s}*(log(P_{after,s}/P_before))^2; VRP_i=ImpliedEventVar_i-ExpectedJumpVar_i-Cost_i`. **Variables/constraints:** s approval/rejection/delay states, p_s probabilities estimated strictly pre-decision; VRP is variance risk premium.

**Data + point-in-time:** FDA event dates, approval histories, pre-event public filings, full options surfaces, equity halt and event-time trades **Decision clock:** No use of FDA outcome until public approval announcement; option quotes at last feasible pre-event time.

**Baseline:** Historical absolute event returns grouped by market cap and indication. **Initial model:** Regulatory-document event taxonomy + shrinkage conditional jump model. **Advanced:** Hierarchical Bayesian decision-state model and option-neutral density decomposition.

**Metrics:** Jump variance calibration, option VRP after costs, event coverage, tail hedge error. **Falsification:** Conditional probability model fails event-matched calibration or net executable option premium.. **Threat:** FDA database daily updates can lag original approval; sample selection, delistings and halted option quotes..

**Execution/capacity:** Biotech option spreads and gap risk severe; define small budget and loss limit before evaluating.. **Proposed tooling:** pymc, scipy, polars, pydantic. **Publication value:** High event-uncertainty methodology; historical quote availability is key.

**Economic sensitivity:** $195k assumed total 24m development/data/maintenance cost; assumed launch in month 9; assumed annual gross outcome downside/base/upside $0k/$110k/$295k. Resulting 24m net ROI **-100.0% / -29.5% / 89.1% (downside/base/upside)**. These are invented transparent sensitivity inputs, not measured ROI, P&L, or investment advice.

**Public starting evidence:** [openFDA Drugs@FDA](https://open.fda.gov/data/drugsfda/); [SEC EDGAR Data Access](https://www.sec.gov/search-filings/edgar-search-assistance/accessing-edgar-data); [Cboe Historical Options Market Statistics](https://www.cboe.com/us/options/market_statistics/historical_data/). **Paid need:** OptionMetrics/OPRA historical executable bid-ask quotes. **Permissioned (never commit):** Approved derivatives margin and short-option risk limits. Status: proposal only; no empirical test, alpha finding or code.

### 17. Sovereign DSA Rating Migration Event Pricing for Frontier Bonds — 89/100 (Global/domestic quant research; Frontier Africa and select emerging Asia sovereign USD credit)
**Decision / economic problem:** Prioritize bond credit watchlists around IMF/World Bank debt sustainability status changes. Debt sustainability publications can update distressed-state probabilities, yet bond prices often incorporate selective pre-announcement leaks.

**Falsifiable H1:** First-public DSA risk-rating changes improve post-publication sovereign credit-loss calibration versus debt/GDP screens.

**Math (proposed):** `Pr(Default_{c,t+h}=1)=logit^{-1}(α+β*DSAChange_{c,t}+γ'ExternalDebt_{c,t}); EL=PD*LGD*EAD`. **Variables/constraints:** c country, DSAChange categorical first-public change, PD conditional default risk, LGD stressed recovery.

**Data + point-in-time:** Country IMF/World Bank public DSA documents, sovereign events, IMF debt statistics, bond quotes and GDP vintages **Decision clock:** Country report posting time and rating applicability; embargo unpublished staff papers and revisions.

**Baseline:** Latest public debt-to-GDP and reserves ratio. **Initial model:** Multi-state ordinal risk migration model with publication-aligned survival validation. **Advanced:** Bayesian sovereign hazard with IMF policy intervention and restructuring recovery scenarios.

**Metrics:** Default Brier score, out-of-time risk precision, spread change, no-trade capacity flags. **Falsification:** No improvement over conservative sovereign ratings baseline, or price move entirely before public timestamp.. **Threat:** DSA coverage selection and program endogeneity, non-tradable distressed bonds, rare default events..

**Execution/capacity:** Frontier bond sizes/spreads can defeat excess returns; focus risk-control research first.. **Proposed tooling:** lifelines, pymc, statsmodels, pandas. **Publication value:** High sovereign risk paper with publication timing and rare-event caution.

**Economic sensitivity:** $175k assumed total 24m development/data/maintenance cost; assumed launch in month 9; assumed annual gross outcome downside/base/upside $0k/$85k/$270k. Resulting 24m net ROI **-100.0% / -39.3% / 92.9% (downside/base/upside)**. These are invented transparent sensitivity inputs, not measured ROI, P&L, or investment advice.

**Public starting evidence:** [IMF Sovereign Risk/DSA Publications](https://www.imf.org/en/publications/dsa/sovereign-risk-and-debt-sustainability-analysis-for-market-access-countries); [World Bank Public DSA Country Repository](https://www.worldbank.org/en/programs/debt-toolkit/dsa). **Paid need:** Frontier sovereign historical bid/ask, CDS and restructuring claims. **Permissioned (never commit):** Authorized sovereign portfolio allocations and eligibility. Status: proposal only; no empirical test, alpha finding or code.

### 18. US Bank Deposit Beta and Mark-to-Market Securities Run Risk — 88/100 (Global/domestic quant research; US regional banks and bank-sector equity/credit)
**Decision / economic problem:** Assess which banks face funding-cost and securities-loss convexity under uninsured deposit migration. Reported uninsured deposits and HTM unrealized losses alone do not measure repricing speed or franchise response.

**Falsifiable H1:** A joint deposit-beta and securities mark-to-market gap predicts earnings/credit deterioration better than uninsured deposit percentage.

**Math (proposed):** `NII_i≈Loans_i*r_L - Deposits_i*(r_D0+β_i*Δr) - Wholesale_i*r_W ; StressGap_i=HTMLoss_i+RunOutflow_i*FundingSpread`. **Variables/constraints:** β_i deposit repricing elasticity, HTMLoss published held-to-maturity unrealized loss proxy, RunOutflow scenario.

**Data + point-in-time:** FDIC bank Call Reports, quarterly uninsured deposits, HTM/AFS loss fields, benchmark rates, bank equity CDS **Decision clock:** Quarter-end balances become usable only at the first public Call Report publication, not period end.

**Baseline:** Uninsured deposit share plus book capital ratio. **Initial model:** Hierarchical deposit beta estimation plus accounting-based duration stress. **Advanced:** Agent-based depositor migration with liquidity haircut and contagion sensitivity.

**Metrics:** Next-quarter NII loss, downside rank precision, capital shortfall, sector-neutral return IC. **Falsification:** No incremental forecast versus capital/deposit mix baseline after strict public release lag.. **Threat:** Quarterly revisions, mergers, bank survivorship and missing bank-specific deposit pricing..

**Execution/capacity:** Large regional bank equity/cash bonds viable; small banks thin, CDS pricing inaccessible and not required for public proxy.. **Proposed tooling:** statsmodels, polars, pymc, duckdb. **Publication value:** Medium-high financial stability research with clear accounting invariants.

**Economic sensitivity:** $155k assumed total 24m development/data/maintenance cost; assumed launch in month 6; assumed annual gross outcome downside/base/upside $0k/$120k/$245k. Resulting 24m net ROI **-100.0% / 16.1% / 137.1% (downside/base/upside)**. These are invented transparent sensitivity inputs, not measured ROI, P&L, or investment advice.

**Public starting evidence:** [FDIC Bank Financial Reports](https://www.fdic.gov/bank-financial-reports); [FRED Data Portal](https://fred.stlouisfed.org/). **Paid need:** Bank funding rate panels and credit spread datasets. **Permissioned (never commit):** Authorized bank exposures, no private depositor/account data. Status: proposal only; no empirical test, alpha finding or code.

### 19. OPEC Oil Balance Residuals and Refined Crack-Spread Transmission — 87/100 (Global/domestic quant research; OPEC producers, global crude and Atlantic Basin refined products)
**Decision / economic problem:** Hedge product crack spreads when public crude production and stock-flow residuals imply inventory stress. Production announcements are not physical barrels; apparent balance discrepancies may reflect reporting lags and revision practices.

**Falsifiable H1:** JODI stock-flow residuals after publication improve future refined crack-spread risk forecasts over oil price and seasonal inventories.

**Math (proposed):** `Residual_{c,m}=Production+Imports-Exports-RefineryIntake-ΔStocks-OtherUse; Crack_t=P_product_t-ConversionRatio*P_crude_t`. **Variables/constraints:** c country,m reporting month; residual is diagnostic with units normalized; price conversion reflects barrel yields.

**Data + point-in-time:** JODI monthly crude stocks/flows, OPEC reports, EIA refinery/product balances, crack-futures settlements **Decision clock:** JODI typically publishes next-month and revises; align release date, not reporting month; execute only after release.

**Baseline:** Seasonal EIA weekly inventories and oil curve. **Initial model:** Constrained oil balance reconciliation and local-projection crack spread model. **Advanced:** Multi-region Bayesian trade flow accounting with measurement error and shipping lags.

**Metrics:** Out-of-sample crack variance forecast, economic hedge cost, stock-balance residual stability. **Falsification:** Residual predictive content disappears after vintages, shipping lags and front-month liquidity adjustment.. **Threat:** Monthly country submission corrections, unit conversion mismatches and sanctioned flow missingness..

**Execution/capacity:** Use executable refined product futures, contract rolls, inventory and liquidity spreads; no inference from paper spreads.. **Proposed tooling:** pandas, statsmodels, scipy.optimize, pymc. **Publication value:** High physical-market accounting and causal commodity term structure.

**Economic sensitivity:** $170k assumed total 24m development/data/maintenance cost; assumed launch in month 7; assumed annual gross outcome downside/base/upside $0k/$115k/$280k. Resulting 24m net ROI **-100.0% / -4.2% / 133.3% (downside/base/upside)**. These are invented transparent sensitivity inputs, not measured ROI, P&L, or investment advice.

**Public starting evidence:** [JODI-Oil World Database Downloads](https://www.jodidata.org/oil/database/data-downloads.aspx); [US EIA Public API](https://www.eia.gov/opendata/v1/). **Paid need:** ICE/NYMEX refined product and crude futures settlement histories. **Permissioned (never commit):** Approved energy derivatives trade limits/costs. Status: proposal only; no empirical test, alpha finding or code.

### 20. Arbitrage-Free Equity Volatility Surface Repair Across Markets — 86/100 (Global/domestic quant research; US, UK and Japan equity index listed options)
**Decision / economic problem:** Produce arbitrage-consistent option risk surfaces and screen put-call/calendar violations before risk budgeting. Sparse option quotes violate calendar and butterfly constraints due to stale prices, holidays and different exercise conventions.

**Falsifiable H1:** Constrained surface repair reduces downstream hedge Greeks error and false arbitrage alarms versus independent spline fitting.

**Math (proposed):** `min_{σ_surface} Σ_{k,T} w_{k,T}(σ_{k,T}-σ_mid)^2 + λ*Smooth(σ) s.t. ∂_T TotalVar≥0, ConvexCall(K,T)≥0`. **Variables/constraints:** k log-forward moneyness,T maturity; σ implied vol, w quote reliability; bounds depend on option exercise type.

**Data + point-in-time:** Time-synchronized option bid/ask, underlying forwards, dividends, exchange calendars, corporate action adjustments **Decision clock:** Quote timestamp aligned to each exchange session; repair uses no quotes from future or closed-market snapshots.

**Baseline:** Per-expiry unconstrained cubic interpolation with clip to bid/ask. **Initial model:** Static no-arbitrage SVI/SSVI constrained calibration with conservative quote filters. **Advanced:** Joint multi-market neural stochastic volatility calibrated to arbitrage constraints and holidays.

**Metrics:** Static arbitrage violations, held-out option price MAE, hedge delta error, false anomaly alerts. **Falsification:** Constrained repair does not reduce out-of-sample pricing/hedging error or introduces hidden quote crossings.. **Threat:** American vs European option styles, dividend marks, early exercise, restricted historical quote rights..

**Execution/capacity:** Surface repairs support quality/risk decisions first; apparent arbitrage cannot be traded without depth and cost.. **Proposed tooling:** numpy, scipy.optimize, jax, QuantLib. **Publication value:** High applied numerical finance with auditable negative tests, but licensed history required.

**Economic sensitivity:** $185k assumed total 24m development/data/maintenance cost; assumed launch in month 8; assumed annual gross outcome downside/base/upside $0k/$105k/$265k. Resulting 24m net ROI **-100.0% / -24.3% / 91.0% (downside/base/upside)**. These are invented transparent sensitivity inputs, not measured ROI, P&L, or investment advice.

**Public starting evidence:** [Cboe Historical Options Market Statistics](https://www.cboe.com/us/options/market_statistics/historical_data/); [Cboe delayed options data restrictions](https://www.cboe.com/delayed_quotes/FREE/quote_table/). **Paid need:** Licensed cross-exchange historical option chains, forward curves and bid-ask depths. **Permissioned (never commit):** Approved option market-making Greeks and trade limits. Status: proposal only; no empirical test, alpha finding or code.


## Portfolio-level guardrails
Exactly ten ideas per group and unique hypotheses were compared with 75 earlier archived titles as of this run; every new study changes the target decision or causal mechanism. Cross-idea economic benefit scenarios cannot be summed because they may overlap. No trading recommendation is made. Source portals checked 2026-11-23; no datasets, pricing, papers or backtests independently downloaded and analyzed.
