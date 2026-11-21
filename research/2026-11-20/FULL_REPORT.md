# Full twenty-idea research report — Batch 16
**Research designs, not tested strategies.** No paper, benchmark, market-data download, solver validation or profit claim is implied.

## 01. Cyber-Outage Contingent Repo Funding Recovery Routes — Securities Finance (priority 96/100)
- **Market / geography:** US cleared and tri-party repo.
- **Problem and decision:** A temporary lender or settlement-node cyber outage can strand otherwise sound secured funding even with sufficient collateral. **Decision:** Pre-approve alternate cash-lender/clearing routes and reserve a minimum contingency liquidity buffer for an exogenous operational outage.
- **Falsifiable H1:** Conditional multi-route recovery decreases funding shortfall and expected disruption cost more than an equal-cost static backup buffer.
- **Equation:** `min_{x,b} E_s[ FundingGap_s(x,b)*p_s + SwitchingCost_s(x) ] + CarryCost(b)`. **Variable/constraint meanings:** x are route and lender allocation decisions, b is reserved liquidity, p_s is the unit shortfall penalty in outage scenario s; legal availability, committed limits and collateral eligibility bound x.
- **Data and granularity:** Timestamped anonymized funding route uptime, fallback approvals, cutoff times, public OFR repo volumes/rates, synthetic outage schedules. Grain: route × lender class × hourly outage scenario.
- **Decision clock:** OFR cleared rate/volume normally T+1 and tri-party T+2, so use public series as lagged calibration only; route outage telemetry must be timestamped pre-decision.
- **Feasible baseline / candidate / advanced:** Fixed 10% contingency funding buffer with one permitted fallback / Two-stage robust multi-commodity flow with cyber failure scenarios / Distributionally robust scenario-tree route control with simultaneous correlated cash-lender disruptions.
- **Metrics:** shortfall dollars, p95 duration, liquidity carry, fail probability, recovery cost. **Explicit no-go:** Held-out synthetic/approved outage replay fails to reduce mean + tail shortfall at fixed total contingency cost.
- **Execution/capacity:** Route/credit limits, settlement windows, cleared access and fallback switching charges; no publicly executable orders.
- **Difficulty/feasibility/publication:** High / Conditional / Stochastic financial network recovery and operational shock simulation.
- **24-month illustrative screening:** $220k hypothetical total 24-month labor/data/compute/compliance cost; rollout begins after 9 months; annual gross benefit scenarios $0k / $180k / $340k (downside/base/upside) for the remaining 1.25 years. Net ROI=(benefit×active years−cost)/cost = -100.0% / 2.3% / 93.2%. These figures are scenario *assumptions*, not expected value, observed alpha, institutional revenue, or forward predictions.
- **Risk:** Public aggregates cannot recover the bank-level cash-lender network or prove an actual route is legally available.
- **Public source entry:** [OFR working paper — Short Circuiting Short-Term Funding](https://www.financialresearch.gov/working-papers/2026/02/10/short-circuiting-short-term-funding/) · [OFR U.S. Repo Markets Data Release](https://www.financialresearch.gov/short-term-funding-monitor/datasets/repo/) · [SEC Treasury Clearing Implementation](https://www.sec.gov/featured-topics/treasury-clearing-implementation); granular availability/licensing unverified.
- **Novelty vs archive:** Distinct from batch-15 benchmark-outage monitoring: this optimizes funding continuity under cyber node failure, not price publication.
- **Full agent/engineering files:** [idea folder](./01-repo-cyber-funding-recovery/README.md).

## 02. Reg SHO Locate Evidence and Borrow-Capacity Audit Engine — Securities Finance (priority 95/100)
- **Market / geography:** US equity securities lending and short-sale compliance.
- **Problem and decision:** A live quote, locate assurance and subsequent borrow fill are not interchangeable, and records may cross inconsistent clocks or quantities. **Decision:** Block or escalate a short-sale request if contemporaneous legally qualifying locate evidence or remaining documented quantity is insufficient.
- **Falsifiable H1:** Event-sourced evidence reconstruction detects noncompliant or capacity-exhausted locates earlier than end-of-day exception review without excess false rejects.
- **Equation:** `min_policy c_FN*FN + c_FP*FP + c_D*Delay subject to permitted(request,t)<=documented_available_qty(t)`. **Variable/constraint meanings:** FN is an incorrectly accepted exception, FP an incorrectly blocked valid locate, and Delay is processing latency; all compliance rules require human-verified effective policy and exemptions.
- **Data and granularity:** Synthetic short-sale order events, documented locate timestamps, source identity, shares remaining, exemptions and post-trade recalls; later private desk records only if approved. Grain: short-sale request × account × security × source × event timestamp.
- **Decision clock:** Locate documentation and quantity must be timestamped before short sale; revised records cannot retroactively authorize prior orders.
- **Feasible baseline / candidate / advanced:** End-of-day deterministic locate exception SQL rules / Typed event-sourcing finite-state verification with causal explainability / Conformal anomaly scoring for ambiguous evidence routed to human review, never autonomous compliance override.
- **Metrics:** prevented invalid requests, false blocks, recall error, audit completion time, p99 latency. **Explicit no-go:** Fails to flag intentionally missing/expired/overused locates on synthetic fixtures or blocks materially more valid trades than comparator.
- **Execution/capacity:** Low per-request CPU; overhead per manual escalation and strict audit storage/retention authorization.
- **Difficulty/feasibility/publication:** Medium / High for synthetic prototype / Temporal formal verification of short-sale locate evidence.
- **24-month illustrative screening:** $120k hypothetical total 24-month labor/data/compute/compliance cost; rollout begins after 6 months; annual gross benefit scenarios $0k / $115k / $200k (downside/base/upside) for the remaining 1.5 years. Net ROI=(benefit×active years−cost)/cost = -100.0% / 43.8% / 150.0%. These figures are scenario *assumptions*, not expected value, observed alpha, institutional revenue, or forward predictions.
- **Risk:** Reg SHO exemptions, broker responsibilities and settlement rules require qualified legal interpretation.
- **Public source entry:** [SEC Regulation SHO locate FAQ](https://www.sec.gov/rules-regulations/staff-guidance/trading-markets-frequently-asked-questions-8); granular availability/licensing unverified.
- **Novelty vs archive:** Unlike old loan-fee selection correction, tests documentation/quantity compliance and audit proof, not fair value or pricing.
- **Full agent/engineering files:** [idea folder](./02-short-locate-evidence-audit/README.md).

## 03. Tokenized Treasury Collateral DvP Finality and Fallback Stress — Securities Finance (priority 94/100)
- **Market / geography:** US Treasury collateral, DTC-tokenized entitlements and conventional settlement.
- **Problem and decision:** Tokenized entitlements introduce chain/wallet/finality distinctions not present in ordinary book-entry Treasury repo workflow. **Decision:** Select permitted collateral settlement pathway with provable delivery-versus-payment, finality and fail-safe fallback.
- **Falsifiable H1:** A permissioned DvP route with explicit finality state and contingency transfer reduces stress settlement lockup against conventional-only or optimistic atomic-claim baselines.
- **Equation:** `min_r E[LockedLiquidityHours_r*FundingRate + FailedSettlementCost_r + ReversionCost_r]`. **Variable/constraint meanings:** r is a legally eligible path; require validated ownership, wallet permission, finality evidence, and a deterministic fallback if one leg fails.
- **Data and granularity:** DTCC published service documentation, synthetic token mint-burn and conventional DvP events, validation proofs, cutoff windows and rehypothecation eligibility. Grain: collateral lot × settlement leg × wallet/ledger state × timestamp.
- **Decision clock:** Use current production DTS service scope as of actual published date; planned 2027 integrations are NOT usable at a 2026 decision time.
- **Feasible baseline / candidate / advanced:** Conventional permitted book-entry DvP with settlement cutoff / Timed Petri net state-machine model of mint/transfer/burn and escrow/finality rules / Formal model checking of cross-system DvP atomicity with stochastic disruption transitions.
- **Metrics:** liquidity-hours locked, failed atomicity scenarios, rollback time, eligible-settlement capacity. **Explicit no-go:** Cannot demonstrate legal/technical atomicity on synthetic fail-mid-transfer tests, or route fails to save liquidity net of controls.
- **Execution/capacity:** Low experimental prototype capacity; real wallet, custody, settlement access and legal finality are gated by service rules.
- **Difficulty/feasibility/publication:** Very high / Medium for research simulation / Cross-ledger settlement-state formal methods and liquidity stress.
- **24-month illustrative screening:** $260k hypothetical total 24-month labor/data/compute/compliance cost; rollout begins after 12 months; annual gross benefit scenarios $0k / $160k / $430k (downside/base/upside) for the remaining 1 years. Net ROI=(benefit×active years−cost)/cost = -100.0% / -38.5% / 65.4%. These figures are scenario *assumptions*, not expected value, observed alpha, institutional revenue, or forward predictions.
- **Risk:** Token entitlements must not be treated as interchangeable with every conventional collateral/clearing agreement.
- **Public source entry:** [DTCC Tokenization Service Hub](https://www.dtcc.com/products-and-services/digital-assets/tokenization/hub) · [DTCC multi-chain integration announcement](https://www.dtcc.com/press-releases/2026/dtcc-tokenization-service-to-connect-with-solana) · [SEC Treasury Clearing Implementation](https://www.sec.gov/featured-topics/treasury-clearing-implementation); granular availability/licensing unverified.
- **Novelty vs archive:** No prior batch models token entitlement lifecycle or cross-ledger DvP/finality; not equivalent to calendar bridging or cross-book identity.
- **Full agent/engineering files:** [idea folder](./03-tokenized-treasury-dvp-fallback/README.md).

## 04. European CSDR Penalty-Aware Settlement Queue Prioritization — Securities Finance (priority 92/100)
- **Market / geography:** EU CSD securities settlement / securities finance return legs.
- **Problem and decision:** Unranked settlement queues may spend scarce intraday capacity on low-penalty legs while high-liability fails remain unresolved. **Decision:** Prioritize settlement instructions under explicit penalty eligibility and scarce processing resources.
- **Falsifiable H1:** A rule-aware queue policy lowers expected daily penalties and fail duration without worsening operational priority controls relative to FIFO.
- **Equation:** `min_pi E[sum_i penalty_i*1(fail_i at close)+delay_cost_i] subject to legal_priority_i and capacity_t`. **Variable/constraint meanings:** pi is processing sequence, i instruction, penalty_i applies only under effective CSDR exclusions and jurisdictional rules; capacity_t is eligible CSD processing capacity.
- **Data and granularity:** Public ESMA CSDR framework, synthetic ISIN liquidity/penalty groups, settlement instruction cutoff, fail reason and amendment history. Grain: instruction × CSD × ISIN × intended settlement day × decision time.
- **Decision clock:** Penalty exclusions and rules must reflect versions legally in force before each instruction decision; ESMA technical advice is not automatically operative law.
- **Feasible baseline / candidate / advanced:** FIFO or largest-notional-first allowed settlement priority / Constrained weighted-shortest-processing-time queue policy with eligibility rules / Approximate dynamic programming under stochastic matched delivery arrival times.
- **Metrics:** penalty liability, fail-days, priority-rule violations, operational throughput. **Explicit no-go:** No statistically measurable improvement in held-out synthetic and later approved settlement scenarios under equal capacity.
- **Execution/capacity:** Settlement bandwidth/available inventory and mandatory processing priority; adverse-penalty reallocations cannot violate service commitments.
- **Difficulty/feasibility/publication:** Medium-high / High as rule-replay prototype / Legal-constraint-aware stochastic queue scheduling.
- **24-month illustrative screening:** $145k hypothetical total 24-month labor/data/compute/compliance cost; rollout begins after 7 months; annual gross benefit scenarios $0k / $100k / $250k (downside/base/upside) for the remaining 1.4166666666666667 years. Net ROI=(benefit×active years−cost)/cost = -100.0% / -2.3% / 144.3%. These figures are scenario *assumptions*, not expected value, observed alpha, institutional revenue, or forward predictions.
- **Risk:** Misclassification of non-attributable fail causes or legal exclusion yields incorrect optimized queues.
- **Public source entry:** [ESMA CSDR Article 7 settlement-fail measures](https://www.esma.europa.eu/publications-and-data/interactive-single-rulebook/csdr/article-7-measures-address-settlement-0) · [ESMA cash penalty scope technical advice](https://www.esma.europa.eu/node/219934); granular availability/licensing unverified.
- **Novelty vs archive:** Differs from past buy-in-vs-wait timing and settlement contagion: this chooses *ex-ante* multi-instruction processing order under cash penalty rules.
- **Full agent/engineering files:** [idea folder](./04-eu-csdr-penalty-queue-policy/README.md).

## 05. ETF Creation/Redemption Basket Shock to Stock-Loan Supply — Securities Finance (priority 91/100)
- **Market / geography:** US equity ETFs and underlying stock loan.
- **Problem and decision:** An ETF primary-market basket can move specific equities and temporarily reshape lendable inventory and market demand independent of secondary price returns. **Decision:** Reserve lendable constituent supply ahead of known or forecasted ETF in-kind redemption/creation windows.
- **Falsifiable H1:** Point-in-time basket-flow measures predict incremental short-horizon available-to-lend changes beyond conventional index membership and short-interest proxies.
- **Equation:** `DeltaSupply_{i,t+h}=alpha_i+beta*BasketsDelta_{i,t}+gamma*Controls_{i,t}+epsilon`. **Variable/constraint meanings:** i is CUSIP, h forecast horizon, basket delta is an appropriately signed and actually available in-kind constituent-flow measure; no lookahead custom basket files.
- **Data and granularity:** ETF disclosed holdings and creation units, public filings, official membership events, licensed AP basket/flows and loan availability for later study. Grain: ETF × constituent × creation/redemption day × publication time.
- **Decision clock:** Only baskets available to a decision-maker before ETF order cutoff may be used; end-of-day holding reports are not morning baskets.
- **Feasible baseline / candidate / advanced:** Change in ETF shares outstanding plus index-event dummy / Hierarchical event study with issuer-basket aggregation and controls / Instrumented flow shock model addressing ETF price-demand endogeneity.
- **Metrics:** inventory forecast MAE, short availability calibration, incremental net inventory carry, execution slippage. **Explicit no-go:** No incremental held-out inventory signal after availability alignment and underlying stock flow controls.
- **Execution/capacity:** Inventory is limited by mandate, lendability and recalls; transaction fees and timing dominate thin basket effects.
- **Difficulty/feasibility/publication:** High / Medium with licensed data / ETF plumbing and endogenous securities lending supply transmission.
- **24-month illustrative screening:** $190k hypothetical total 24-month labor/data/compute/compliance cost; rollout begins after 9 months; annual gross benefit scenarios $0k / $130k / $280k (downside/base/upside) for the remaining 1.25 years. Net ROI=(benefit×active years−cost)/cost = -100.0% / -14.5% / 84.2%. These figures are scenario *assumptions*, not expected value, observed alpha, institutional revenue, or forward predictions.
- **Risk:** Most executable AP basket details and actual stock-loan supply are not public.
- **Public source entry:** [SEC EDGAR API documentation](https://www.sec.gov/search-filings/edgar-application-programming-interfaces) · [SEC developer resources and disclosure revisions](https://www.sec.gov/search-filings/edgar-search-assistance/accessing-edgar-data); granular availability/licensing unverified.
- **Novelty vs archive:** Distinct from synthetic borrow put-call parity and owner's co-withdrawal risk; identifies ETF primary basket supply as separate driver.
- **Full agent/engineering files:** [idea folder](./05-etf-basket-stockloan-flow/README.md).

## 06. Noncash Collateral Correlation-Cluster Haircut Controller — Securities Finance (priority 90/100)
- **Market / geography:** Multi-asset collateral supporting US/EU securities loans.
- **Problem and decision:** Static issuer/security-class haircuts can understate simultaneous stress of correlated noncash collateral while overhaircutting diversified pools. **Decision:** Recommend minimum defensive haircuts for a collateral basket based on joint concentration and liquidation correlation.
- **Falsifiable H1:** Cluster-aware chance constraints produce lower stressed shortfall than sector-flat haircuts at a matched average financing cost.
- **Equation:** `min_h CarryCost(h) subject to P(Loss(Collateral,Loan,h)>Limit)<=alpha and issuer_weight<=cap`. **Variable/constraint meanings:** h is haircut vector, alpha tolerated tail probability and cap issuer concentration; credit/legal eligibility are hard constraints.
- **Data and granularity:** Approved collateral constituents, synthetic issuer cross-holdings, stressed factor returns, liquidation bid/ask, haircut and legal threshold. Grain: collateral security × issuer cluster × loan exposure × as-of time.
- **Decision clock:** Apply only return histories, prices, group linkages and issuer memberships known at the decision timestamp.
- **Feasible baseline / candidate / advanced:** Uniform issuer/asset-class static haircut / Scenario CVaR optimization with issuer cluster caps / Distributionally robust ambiguity-set CVaR with wrong-way liquidity correlation.
- **Metrics:** shortfall ES, collateral usage, haircut turnover, stress exceptions. **Explicit no-go:** Risk benefit disappears when using stressed-correlation holdouts or violates legal haircut floors.
- **Execution/capacity:** Financing spread effects, haircuts, asset transfer restrictions, concentration penalties and market impact.
- **Difficulty/feasibility/publication:** High / Medium with approved data / Distributionally robust collateral concentration and shadow financing cost.
- **24-month illustrative screening:** $210k hypothetical total 24-month labor/data/compute/compliance cost; rollout begins after 9 months; annual gross benefit scenarios $0k / $145k / $320k (downside/base/upside) for the remaining 1.25 years. Net ROI=(benefit×active years−cost)/cost = -100.0% / -13.7% / 90.5%. These figures are scenario *assumptions*, not expected value, observed alpha, institutional revenue, or forward predictions.
- **Risk:** Asset covariance may break exactly when haircuts are needed and public free-float proxies omit liquidation controls.
- **Public source entry:** [OFR U.S. Repo Markets Data Release](https://www.financialresearch.gov/short-term-funding-monitor/datasets/repo/) · [BIS/CPMI-IOSCO Principles for Financial Market Infrastructures](https://www.bis.org/committees/cpmi/pfmi/overview); granular availability/licensing unverified.
- **Novelty vs archive:** Not stale-mark quarantine (price integrity) or wrong-way *borrower default* risk: chooses collateral cluster haircut policy at portfolio level.
- **Full agent/engineering files:** [idea folder](./06-noncash-collateral-cluster-haircuts/README.md).

## 07. CCP Default-Fund Mutualization Marginal Risk Budget — Securities Finance (priority 89/100)
- **Market / geography:** US/EU Treasury and derivatives clearing memberships.
- **Problem and decision:** Central clearing moves bilateral exposure into waterfall and replenishment obligations that cannot be represented solely by initial-margin savings. **Decision:** Set internal clearing exposure budgets based on potential default-fund replenishment and contingent mutualized-loss allocation.
- **Falsifiable H1:** A conservative tail contribution metric improves risk-adjusted clearing exposure allocation against nominal balance or posted-margin controls.
- **Equation:** `RiskCharge_j=ES_alpha(sum_s MutualizedLoss_{j,s} + Replenishment_{j,s})`. **Variable/constraint meanings:** j clearing membership or CCP, s default scenario, alpha stress-tail quantile; actual waterfall order and limits are CCP specific.
- **Data and granularity:** Public CPMI/IOSCO disclosure framework, synthetic member default distributions, concentration factors, CCP product eligibility and fee schedules. Grain: CCP membership × cleared product × default stress scenario.
- **Decision clock:** Use published CCP rulebooks and dated quantitative disclosures only when released; past final stress reports cannot enter historical decisions early.
- **Feasible baseline / candidate / advanced:** Exposure limit proportional to initial margin only / Transparent worst-two-member default waterfall simulator / Coherent-risk allocation via Shapley/gradient ES under correlated default network scenarios.
- **Metrics:** tail capital charge, stress shortfall, liquidity buffer usage, net clearing benefit. **Explicit no-go:** No material differentiation in conditional tail loss versus margin-only limits after conservative parameter uncertainty.
- **Execution/capacity:** Default fund and extra margin liquidity headroom, clearing fees and enforceable contribution caps.
- **Difficulty/feasibility/publication:** Very high / Medium as stress research / Mutualized default-waterfall risk attribution across clearing portfolios.
- **24-month illustrative screening:** $240k hypothetical total 24-month labor/data/compute/compliance cost; rollout begins after 11 months; annual gross benefit scenarios $0k / $125k / $325k (downside/base/upside) for the remaining 1.0833333333333333 years. Net ROI=(benefit×active years−cost)/cost = -100.0% / -43.6% / 46.7%. These figures are scenario *assumptions*, not expected value, observed alpha, institutional revenue, or forward predictions.
- **Risk:** Actual default fund contributions and replenishment terms may differ from public examples and vary by venue.
- **Public source entry:** [BIS/CPMI-IOSCO Principles for Financial Market Infrastructures](https://www.bis.org/committees/cpmi/pfmi/overview) · [SEC Treasury Clearing Implementation](https://www.sec.gov/featured-topics/treasury-clearing-implementation); granular availability/licensing unverified.
- **Novelty vs archive:** Unlike 2026-11-13 clearing access-path duplicate-margin optimizer, this prices mutualized *default-fund tail loss*.
- **Full agent/engineering files:** [idea folder](./07-ccp-default-fund-tail-budget/README.md).

## 08. SFTR Reporting Regime Drift and Public-Private Divergence Detector — Securities Finance (priority 88/100)
- **Market / geography:** European securities financing transaction repositories.
- **Problem and decision:** Registry revisions and reporting practice changes can masquerade as repo/securities-lending market shifts. **Decision:** Detect structural reporting-quality breaks before using reported SFTR aggregates as market exposure signals.
- **Falsifiable H1:** Joint change-point tests on volumes, missingness and reported collateral taxonomy identify synthetic or historical reporting breaks more reliably than absolute-value outlier rules.
- **Equation:** `Alarm_t=1{PosteriorP(change|feature_history)>q}; minimize detection_delay+lambda*false_alarms`. **Variable/constraint meanings:** q is alarm threshold chosen before holdout; changes attributed to reporting are hypotheses until repository audit.
- **Data and granularity:** ESMA reporting rules and publications, public aggregate exposures where available, historical methodology changes, synthetic backdated schema versions. Grain: SFTR public aggregate series × jurisdiction × report vintage.
- **Decision clock:** Use publication timestamps and repository versions, not reporting reference dates; detailed transaction data are supervisor-restricted.
- **Feasible baseline / candidate / advanced:** Fixed ±3-sigma z-score alert on each series / Robust multivariate Bayesian online change-point detection / Hierarchical regime/missingness change-point models with document version embeddings as covariates.
- **Metrics:** break detection delay, false alarms, post-correction economic interpretation stability. **Explicit no-go:** Synthetic change fixtures not detected within agreed delay or false alerts exceed preregistered burden.
- **Execution/capacity:** Low runtime; review cost per alert and regulator/source availability dominate feasibility.
- **Difficulty/feasibility/publication:** Medium / High for aggregate checks / Public regulatory-data integrity and market microstructure inference.
- **24-month illustrative screening:** $135k hypothetical total 24-month labor/data/compute/compliance cost; rollout begins after 6 months; annual gross benefit scenarios $0k / $90k / $190k (downside/base/upside) for the remaining 1.5 years. Net ROI=(benefit×active years−cost)/cost = -100.0% / 0.0% / 111.1%. These figures are scenario *assumptions*, not expected value, observed alpha, institutional revenue, or forward predictions.
- **Risk:** Only public aggregate data may be available, making root-cause verification incomplete.
- **Public source entry:** [ESMA Securities Financing Transactions Reporting](https://www.esma.europa.eu/data-reporting/sftr-reporting) · [ESMA trade-repository SFTR enforcement release](https://www.esma.europa.eu/press-news/esma-news/esma-sanctions-regis-tr-serious-breaches-organisational-obligations); granular availability/licensing unverified.
- **Novelty vs archive:** Prior identity reconciliation matches transactions across books; this detects public reporting *regime and taxonomy changes*.
- **Full agent/engineering files:** [idea folder](./08-sftr-reporting-regime-drift/README.md).

## 09. Evergreen Repo Early-Termination Optionality Risk Budget — Securities Finance (priority 87/100)
- **Market / geography:** Open and evergreen secured funding agreements.
- **Problem and decision:** Contractual call/notice periods create embedded funding options not captured by standard fixed-maturity repo carry. **Decision:** Set rate/tenor risk charges for unilateral termination and extension rights in open repo or evergreen funding.
- **Falsifiable H1:** Notice-option-adjusted funding pricing reduces out-of-sample replacement-cost surprises versus duration-only term curve cost.
- **Equation:** `V_t=max(ExerciseValue_t, Carry_t+discount*E_t[V_{t+1}]) subject to NoticeDays,Eligibility`. **Variable/constraint meanings:** exercise and continuation are contract-party-specific; funder and borrower exercise incentives must be separately simulated.
- **Data and granularity:** Synthetic open-repo terms, public SOFR and OFR repo curve history, legally enforceable reset/termination terms and funding costs. Grain: contract × notice period × funding day × interest-rate state.
- **Decision clock:** Public repo rates have release lags; exact contract termination rights must be known at contract initiation, not retrofitted.
- **Feasible baseline / candidate / advanced:** Static repo spread plus deterministic notice-day funding reserve / Least-squares Monte Carlo for bilateral asymmetric stop decisions / Nonzero-sum stochastic game with liquidity-dependent termination intensities.
- **Metrics:** replacement funding loss, option premium calibration, cash-flow stress, tail liquidity gap. **Explicit no-go:** Option charge unstable or no improvement over conservative notice reserve in stress holdouts.
- **Execution/capacity:** Bilateral notice terms, term borrowing capacity, haircuts and closeout spreads constrain exercise decisions.
- **Difficulty/feasibility/publication:** High / Medium / Bilateral termination-option pricing in secured funding.
- **24-month illustrative screening:** $180k hypothetical total 24-month labor/data/compute/compliance cost; rollout begins after 10 months; annual gross benefit scenarios $0k / $105k / $270k (downside/base/upside) for the remaining 1.1666666666666667 years. Net ROI=(benefit×active years−cost)/cost = -100.0% / -31.9% / 75.0%. These figures are scenario *assumptions*, not expected value, observed alpha, institutional revenue, or forward predictions.
- **Risk:** Non-observed counterparty exercise behavior; public term repo alone does not identify proprietary notice clauses.
- **Public source entry:** [OFR U.S. Repo Markets Data Release](https://www.financialresearch.gov/short-term-funding-monitor/datasets/repo/) · [SEC Treasury Clearing Implementation](https://www.sec.gov/featured-topics/treasury-clearing-implementation); granular availability/licensing unverified.
- **Novelty vs archive:** Prior repo term-structure forecasting models *fixed-tenor spreads*; this values unilateral open-term exercise mechanics.
- **Full agent/engineering files:** [idea folder](./09-evergreen-repo-termination-option/README.md).

## 10. Securities-Lending Circular Flow Surveillance via Temporal Graphs — Securities Finance (priority 86/100)
- **Market / geography:** Multi-agent securities loans and collateral transfers; US/EU.
- **Problem and decision:** Pairwise exception rules can miss cyclic chains of small loans and rapid reversals through multiple legal counterparties. **Decision:** Escalate suspicious short-lived circular borrow/return patterns for compliance review without inferring wrongdoing from volume alone.
- **Falsifiable H1:** Causal temporal-motif alerts improve precision at fixed review capacity over pairwise round-trip thresholds in seeded synthetic cases.
- **Equation:** `min_alertPolicy ReviewCost + MissCost subject to ReviewCapacity<=K and no autonomously adverse action`. **Variable/constraint meanings:** K is review budget; temporal motif score must be conditioned on legitimate inventory transfers and settlement cycles.
- **Data and granularity:** Synthetic multi-party loan/return event graph, matched collateral movement, legitimate transfer controls, anonymized case annotations if permitted. Grain: synthetic securities loan transfer edge × security × event timestamp.
- **Decision clock:** Create graph only from recorded transfers visible before alert time; disallow knowledge of subsequent investigation outcomes in features.
- **Feasible baseline / candidate / advanced:** Two-party net-quantity turnaround rules / Temporal graph motif detection with exact deterministic event identity / Weakly supervised dynamic graph anomaly ranking with human-in-loop conformal calibration.
- **Metrics:** precision at K, seeded motif recall, legitimate-flow false-alerts, explanation fidelity. **Explicit no-go:** No precision@K gain against pairwise rules under benign high-volume churn fixtures.
- **Execution/capacity:** Compliance analyst review capacity and evidentiary retention, no automatic client suspension.
- **Difficulty/feasibility/publication:** High / Medium with strict controls / Temporal graph surveillance with constrained false accusations.
- **24-month illustrative screening:** $165k hypothetical total 24-month labor/data/compute/compliance cost; rollout begins after 9 months; annual gross benefit scenarios $0k / $95k / $240k (downside/base/upside) for the remaining 1.25 years. Net ROI=(benefit×active years−cost)/cost = -100.0% / -28.0% / 81.8%. These figures are scenario *assumptions*, not expected value, observed alpha, institutional revenue, or forward predictions.
- **Risk:** False accusations, privileged customer data, and severe sample-selection bias in investigated cases.
- **Public source entry:** [ESMA Securities Financing Transactions Reporting](https://www.esma.europa.eu/data-reporting/sftr-reporting) · [SEC Regulation SHO locate FAQ](https://www.sec.gov/rules-regulations/staff-guidance/trading-markets-frequently-asked-questions-8); granular availability/licensing unverified.
- **Novelty vs archive:** Batch-14 cross-book identity reconciler targets *record matching*; this tests suspicious multi-party circular behavior at a fixed review budget.
- **Full agent/engineering files:** [idea folder](./10-seclending-circular-flow-surveillance/README.md).

## 11. Japan FX Intervention Impact and Option-Skew Persistence — Domestic/Global Quant (priority 97/100)
- **Market / geography:** Japan USD/JPY, yen crosses and FX options.
- **Problem and decision:** Official intervention disclosures arrive after execution; a hindsight backtest can misrepresent a trader's knowledge of actual intervention days. **Decision:** Determine when to reduce/hedge yen exposure following **publicly observed** intervention or subsequent official disclosure.
- **Falsifiable H1:** A release-time-corrected intervention-event measure predicts conditional 1–20-day FX variance/skew adjustment beyond macro announcements and momentum.
- **Equation:** `DeltaSkew_{t,h}=beta*InterventionKnownAt_t+gamma*MacroControls_t+epsilon_{t,h}`. **Variable/constraint meanings:** InterventionKnownAt_t is zero until event is publicly known or release issued; h is forward horizon, and skew is an executable options quote measure.
- **Data and granularity:** MOF monthly/quarterly intervention releases and dates, spot FX, short-term rate differential, timestamped USDJPY options/forward data. Grain: intervention disclosure event × FX option tenor × quote timestamp.
- **Decision clock:** MOF 2026 Q3 intervention details published Nov 9, 2026; never use ex-post intervention date labels in same-day live-time signals.
- **Feasible baseline / candidate / advanced:** Standard spot momentum and monetary-policy announcement dummy / Disclosure-timestamp event study with matched controls and local projections / Partial-identification causal synthetic control separating information, execution and portfolio-flow channels.
- **Metrics:** incremental forward skew/vol forecast skill, delta-hedged net P&L, placebo events, risk-adjusted drawdown. **Explicit no-go:** No differential response versus rate/central-bank news controls on withheld intervention disclosures or net-option-cost results.
- **Execution/capacity:** Executable FX spot/options spreads, liquidity, event jump exposure, market access and derivatives capital.
- **Difficulty/feasibility/publication:** High / High for event research; trade evidence conditional / Identification of FX intervention signaling under delayed official disclosure.
- **24-month illustrative screening:** $180k hypothetical total 24-month labor/data/compute/compliance cost; rollout begins after 8 months; annual gross benefit scenarios $0k / $95k / $240k (downside/base/upside) for the remaining 1.3333333333333333 years. Net ROI=(benefit×active years−cost)/cost = -100.0% / -29.6% / 77.8%. These figures are scenario *assumptions*, not expected value, observed alpha, institutional revenue, or forward predictions.
- **Risk:** Actual intervention execution is not transparently known in real time; small event count undermines causal certainty.
- **Public source entry:** [Japan Ministry of Finance — 2026 Q3 intervention breakdown](https://www.mof.go.jp/english/policy/international_policy/reference/feio/quarter/2026_3Qe.html) · [Japan Ministry of Finance — FX intervention monthly release index](https://www.mof.go.jp/english/policy/international_policy/reference/feio/monthly/index.html); granular availability/licensing unverified.
- **Novelty vs archive:** Distinct from multilingual monetary policy semantic shocks; targets executed FX operations and retrospective labeling bias.
- **Full agent/engineering files:** [idea folder](./11-japan-fx-intervention-persistence/README.md).

## 12. US TIPS CPI Indexation-Lag Carry and Breakeven Calendar Surface — Domestic/Global Quant (priority 95/100)
- **Market / geography:** US TIPS, nominal Treasuries, inflation swaps.
- **Problem and decision:** TIPS index ratio uses reference CPI with publication lag; naïve inflation beta ignores fixed-known indexation accrual and deflation mechanics. **Decision:** Select TIPS versus nominal duration-hedged exposure around CPI index-ratio carry windows.
- **Falsifiable H1:** A vintage-consistent carry decomposition improves matched-duration real-vs-nominal excess-return hedging net of liquidity/rollover costs.
- **Equation:** `TIPSReturn_t=RealYieldReturn_t+KnownIndexAccrual_t+InflationNews_t+LiquidityResidual_t`. **Variable/constraint meanings:** KnownIndexAccrual_t is observable at decision time; carry, breakeven and real-yield exposures require duration scaling and deflation floors.
- **Data and granularity:** Treasury official daily TIPS index ratios/CPI, vintage BLS CPI, nominal/TIPS quotes, issue terms, accrued interest. Grain: TIPS CUSIP × CPI/index-ratio effective date × decision timestamp.
- **Decision clock:** Daily index ratios can be forecast only from already published reference CPI; preserve first release and later corrections.
- **Feasible baseline / candidate / advanced:** Duration-matched TIPS-minus-nominal bond without CPI-calendar signal / Deterministic index-ratio accrual and liquidity-factor attribution / State-space real/nominal curve with stochastic CPI surprise and inflation floor convexity.
- **Metrics:** hedge tracking error, information ratio net of costs, index replication error, carry decomposition residual. **Explicit no-go:** Improvement vanishes versus a carry-only and time-matched duration hedge after execution spread costs.
- **Execution/capacity:** Issue-level depth, coupon accrued interest, repo funding, bid-ask, tax and duration hedging constraints.
- **Difficulty/feasibility/publication:** Medium / High as price replication / Point-in-time inflation-linked bond carry and indexation-lag mispricing decomposition.
- **24-month illustrative screening:** $135k hypothetical total 24-month labor/data/compute/compliance cost; rollout begins after 6 months; annual gross benefit scenarios $0k / $105k / $200k (downside/base/upside) for the remaining 1.5 years. Net ROI=(benefit×active years−cost)/cost = -100.0% / 16.7% / 122.2%. These figures are scenario *assumptions*, not expected value, observed alpha, institutional revenue, or forward predictions.
- **Risk:** Illiquid issue quotations, inflation floor optionality, unrevised CPI data and seasonality overfit.
- **Public source entry:** [U.S. Treasury Fiscal Data — TIPS and CPI](https://fiscaldata.treasury.gov/datasets/tips-cpi-data/) · [SEC EDGAR API documentation](https://www.sec.gov/search-filings/edgar-application-programming-interfaces); granular availability/licensing unverified.
- **Novelty vs archive:** Prior US-Euro sovereign curve shock model decomposes release shocks; this prices U.S. issue-specific TIPS CPI indexation carry.
- **Full agent/engineering files:** [idea folder](./12-us-tips-indexation-lag-carry/README.md).

## 13. EU ETS Auction Supply Revision and Carbon Futures Carry — Domestic/Global Quant (priority 94/100)
- **Market / geography:** EU carbon allowances (EUA), European power utilities.
- **Problem and decision:** Auction calendar revisions and annual compliance data affect expected allowance net supply but are released on distinct clocks. **Decision:** Hedge EUA futures calendar spreads against only announced changes in auction volume and verified-emissions obligations.
- **Falsifiable H1:** Public-vintage auction-volume shocks improve calendar-spread/hedge-risk forecasts beyond front-month momentum and seasonal dummies.
- **Equation:** `Spread_{m,n,t}=theta*(ExpectedAuctionSupply_t - ExpectedComplianceDemand_t)+beta*EnergyControls_t+epsilon_t`. **Variable/constraint meanings:** m,n are contract maturities; expectations only use public revisions available before trade, not full-year realized auction volumes.
- **Data and granularity:** European Commission vintage auction calendars, Union Registry verified emissions/compliance, dated policy changes, EUA/power/gas contract prices. Grain: EU ETS auction calendar publication × allowance futures tenor × exchange quote timestamp.
- **Decision clock:** 2027 auction schedule announced Jul 30 2026; 2025 compliance data public Oct 5 2026; only released data at as-of permitted.
- **Feasible baseline / candidate / advanced:** Calendar-month fixed seasonal allowance spread / Event study of auction schedule revisions and futures risk factors / Partial equilibrium allowance banking model with endogenous industrial abatement and policy scenarios.
- **Metrics:** EUA spread basis MAE, hedged risk reduction, net carry after fees, low-liquidity scenario loss. **Explicit no-go:** No out-of-sample spread forecast or hedge benefit net of spreads after matched energy factors.
- **Execution/capacity:** EUA contract liquidity, expiry rolling, carbon compliance mandates and margin/collateral limits.
- **Difficulty/feasibility/publication:** High / Medium / Carbon allowance bankability, supply revision events and futures term structure.
- **24-month illustrative screening:** $210k hypothetical total 24-month labor/data/compute/compliance cost; rollout begins after 9 months; annual gross benefit scenarios $0k / $125k / $310k (downside/base/upside) for the remaining 1.25 years. Net ROI=(benefit×active years−cost)/cost = -100.0% / -25.6% / 84.5%. These figures are scenario *assumptions*, not expected value, observed alpha, institutional revenue, or forward predictions.
- **Risk:** Policy revision expectations may be priced before official publication; futures/Registry coverage not contemporaneous.
- **Public source entry:** [European Commission — 2026/2027 EU ETS auction calendar](https://climate.ec.europa.eu/news-other-reads/news/revised-2026-and-2027-eu-ets1-auction-calendars-published-2026-07-30_en) · [European Commission — Union Registry](https://climate.ec.europa.eu/areas-action/carbon-markets/eu-emissions-trading-system-eu-ets/union-registry_en); granular availability/licensing unverified.
- **Novelty vs archive:** Not prior European gas storage deliverability; models ETS allowance auction policy supply and carbon forward carry.
- **Full agent/engineering files:** [idea folder](./13-eu-ets-auction-carbon-carry/README.md).

## 14. Korean Household Debt-Service Shock to Bank–Consumer Equity Spread — Domestic/Global Quant (priority 92/100)
- **Market / geography:** South Korea household credit, KOSPI/KOSDAQ banks and consumer discretionary.
- **Problem and decision:** Aggregate debt service can change credit demand, asset quality and retail margins, but effects differ across lender and spending industries. **Decision:** Hedge relative exposure of Korean bank and consumer equities across household debt-service regime changes.
- **Falsifiable H1:** Lag-corrected Korean household DSR changes identify subsequent bank-versus-consumer earnings dispersion beyond policy rates/market beta.
- **Equation:** `RelativeEPS_{b,c,t+h}=a+beta*DSRSurprise_t+gamma*PolicyRate_t+delta*FX_t+epsilon`. **Variable/constraint meanings:** b bank peer basket, c consumer peer basket, h disclosure-to-outcome window; DSRSurprise uses real-time expected vs published DSR, not revised future panels.
- **Data and granularity:** BIS Korea household DSR, BOK/Statistics Korea public lending/rates, issuer earnings and local equity returns, reporting vintage. Grain: quarterly DSR release × issuer × accounting period × price timestamp.
- **Decision clock:** BIS Korean DSR published with quarterly lag (available through 2026-Q1 on checked dataset page); do not trade on 2026-Q2 unless publicly released.
- **Feasible baseline / candidate / advanced:** Equal-beta long banks short consumer discretionary with lagged policy-rate signal / Panel local projections with shrinkage and sector time fixed effects / Dynamic heterogeneous household credit impulse response with instrumented policy-rate shocks.
- **Metrics:** cross-sector earnings forecast delta, beta-neutral IR, worst-regime drawdown, capacity after local spreads. **Explicit no-go:** No stable expected-earnings or beta-neutral sector difference once rates and economy factors are controlled.
- **Execution/capacity:** Local borrow, FX hedge, Korean market access, corporate action history, sector liquidity and taxes.
- **Difficulty/feasibility/publication:** Medium-high / Medium / Household debt-service transmission across bank vs retail profitability.
- **24-month illustrative screening:** $170k hypothetical total 24-month labor/data/compute/compliance cost; rollout begins after 9 months; annual gross benefit scenarios $0k / $105k / $260k (downside/base/upside) for the remaining 1.25 years. Net ROI=(benefit×active years−cost)/cost = -100.0% / -22.8% / 91.2%. These figures are scenario *assumptions*, not expected value, observed alpha, institutional revenue, or forward predictions.
- **Risk:** Endogenous rate policy and sector composition cause confounding; public issuer histories need delisting continuity.
- **Public source entry:** [BIS — South Korea household debt service ratio](https://data.bis.org/topics/DSR/BIS%2CWS_DSR%2C1.0/Q.KR.H); granular availability/licensing unverified.
- **Novelty vs archive:** Distinct from EM external debt currency mismatch and South Africa power reliability; Korean domestic household burden drives cross-sector equity dispersion.
- **Full agent/engineering files:** [idea folder](./14-korea-household-debt-equity-dispersion/README.md).

## 15. Global Shipping Connectivity Re-Routing to Inflation and Equity Margins — Domestic/Global Quant (priority 91/100)
- **Market / geography:** East Asia–Europe–US maritime routes, transport/industrial equity sectors.
- **Problem and decision:** Freight disruption signals are often conflated with trade quantities, while shipping network redundancy alters price transmission under port outages. **Decision:** Size logistics/inflation hedges when public route connectivity and port-service centrality shift.
- **Falsifiable H1:** Route-centrality-adjusted connectivity changes improve delayed goods-inflation and shipper-margin forecasts over raw container volume.
- **Equation:** `DeltaP_{r,t+h}=sum_p Exposure_{r,p}*Shock_{p,t}/(1+AlternateRoutes_{p,t})+epsilon`. **Variable/constraint meanings:** r is importer region, p port corridor; shocks and alternate route count must use actually published index vintage.
- **Data and granularity:** UNCTAD monthly/quarterly liner connectivity, MARAD freight/port dashboards, shipping rate indexes where licensed, CPI/PPI and issuer logistics costs. Grain: country/port route × monthly index release × subsequent inflation/earnings outcome.
- **Decision clock:** UNCTAD latest confirmed index data update Sep 28 2026; a 2026-11-20 decision cannot use December data.
- **Feasible baseline / candidate / advanced:** Aggregate global shipping index versus region CPI with fixed lag / Supply-route network exposure local projections / Causal graph shock transmission with endogenous alternative route capacity and measurement error.
- **Metrics:** inflation nowcast gain, equity margin dispersion, attribution stability and hedged net P&L. **Explicit no-go:** No incremental signal after global industrial production, oil and published trade volume controls.
- **Execution/capacity:** Sector ETF/futures depth, global market close mismatch, FX hedge and rebalance slippage.
- **Difficulty/feasibility/publication:** High / Medium / Shipping network redundancy and inflation pass-through identification.
- **24-month illustrative screening:** $220k hypothetical total 24-month labor/data/compute/compliance cost; rollout begins after 10 months; annual gross benefit scenarios $0k / $135k / $300k (downside/base/upside) for the remaining 1.1666666666666667 years. Net ROI=(benefit×active years−cost)/cost = -100.0% / -28.4% / 59.1%. These figures are scenario *assumptions*, not expected value, observed alpha, institutional revenue, or forward predictions.
- **Risk:** Connectivity is not real-time port congestion and quarterly updates can obscure freight cycle timing.
- **Public source entry:** [UNCTAD — Liner shipping connectivity and updates](https://unctadstat.unctad.org/insights/theme/111) · [U.S. MARAD port data and statistics](https://www.maritime.dot.gov/data-reports/ports); granular availability/licensing unverified.
- **Novelty vs archive:** Batch-14 trade-network export shock model uses reported trade value; this studies route topology and alternate maritime connectivity.
- **Full agent/engineering files:** [idea folder](./15-global-port-connectivity-inflation/README.md).

## 16. Issuer Customer-Concentration Disclosure to Earnings Options Skew — Domestic/Global Quant (priority 90/100)
- **Market / geography:** US listed single-name equity options and SEC 10-K/10-Q issuers.
- **Problem and decision:** A large customer share can create correlated revenue jump exposure not captured by standard sector-level realized volatility. **Decision:** Hedge customer-loss jump risk in companies with concentrated customers using explicitly costed options structures.
- **Falsifiable H1:** Point-in-time EDGAR customer concentration disclosures explain forward options downside skew changes beyond leverage, size and event vol.
- **Equation:** `DownsideSkew_{i,t}=a+beta*CustomerHHI_{i,t-known}+gamma*EventControls_{i,t}+epsilon`. **Variable/constraint meanings:** HHI is sum of squared disclosed customer revenue shares (bounded/partially observed); t-known is filing dissemination time, not fiscal year end.
- **Data and granularity:** SEC EDGAR original issuer filings, customer concentration disclosures, single-stock option surface, earnings calendar, liquidity and corporate actions. Grain: issuer accepted filing × reported customer share × options quote timestamp.
- **Decision clock:** Use SEC acceptance timestamps and first published disclosure, not retroactive tagged XBRL after amended filings.
- **Feasible baseline / candidate / advanced:** Size/leverage/industry/earnings event-only option skew estimator / Censored-disclosure panel with inverse observation probability adjustment / Jump-diffusion structural model of concentrated-customer exit hazard.
- **Metrics:** post-filing skew residual, risk hedge efficiency, delta-neutral net performance and disclosure coverage. **Explicit no-go:** No post-filing incremental skew or hedge gain beyond conventional earnings-related jump risk.
- **Execution/capacity:** Option open interest, bid/ask, assignment/maturity mechanics and volatile event hedging friction.
- **Difficulty/feasibility/publication:** Medium-high / High for disclosure research, trading conditional / Disclosure censoring and implied tail-risk segmentation.
- **24-month illustrative screening:** $160k hypothetical total 24-month labor/data/compute/compliance cost; rollout begins after 9 months; annual gross benefit scenarios $0k / $85k / $260k (downside/base/upside) for the remaining 1.25 years. Net ROI=(benefit×active years−cost)/cost = -100.0% / -33.6% / 103.1%. These figures are scenario *assumptions*, not expected value, observed alpha, institutional revenue, or forward predictions.
- **Risk:** Customer concentrations may be anonymized and nonrandomly omitted; options trade data can be illiquid.
- **Public source entry:** [SEC EDGAR API documentation](https://www.sec.gov/search-filings/edgar-application-programming-interfaces) · [SEC developer resources and disclosure revisions](https://www.sec.gov/search-filings/edgar-search-assistance/accessing-edgar-data); granular availability/licensing unverified.
- **Novelty vs archive:** Prior Japan buyback execution, AI capex and global factors differ from customer-dependent equity jump risk around original filings.
- **Full agent/engineering files:** [idea folder](./16-customer-concentration-options-skew/README.md).

## 17. Public BDC Portfolio Fair-Value Markdown Lead Indicator — Domestic/Global Quant (priority 89/100)
- **Market / geography:** US public BDC equities, leveraged loans and credit sentiment.
- **Problem and decision:** Quarterly fair values of less-liquid loans are not continuous market prices; comparability and valuation lag impair credit monitoring. **Decision:** Prioritize due diligence or credit hedges where public business development company holdings imply delayed loan fair-value marks.
- **Falsifiable H1:** Public issuer-level BDC portfolio mark dispersion identifies future credit event/downgrade risk after controlling for BDC leverage and macro credit spread.
- **Equation:** `RiskScore_{loan,t}=f(PriceToCost_{t},NonAccrual_{t},Sector_{t},FundLag_{t})`. **Variable/constraint meanings:** PriceToCost is reported fair value over cost, nonaccrual flags only as filed, FundLag is filing delay; target is future externally validated credit deterioration.
- **Data and granularity:** Original SEC BDC 10-Q/10-K investment schedules and mark values, sector classification, publicly known credit outcomes and licensed leveraged-loan pricing. Grain: BDC filing × portfolio company/sector × disclosure timestamp.
- **Decision clock:** Use filed investment schedules only after filing acceptance; amendments/revised portfolio marks cannot enter historical quarters.
- **Feasible baseline / candidate / advanced:** BDC aggregate NAV discount and published nonaccrual percentage / Issuer-level mark-hazard panel with censored holdings and missing-not-at-random controls / Hierarchical Bayesian marked-to-market credit migration model with portfolio network dependence.
- **Metrics:** future credit-event AUC/PR, mark-calibration error, NAV stress accuracy, opportunity capacity. **Explicit no-go:** No improvement over current NAV discount/nonaccrual baseline in later quarters or effects only known after financial reports.
- **Execution/capacity:** BDC equity market depth, credit hedging basis, optional loan trading access and stale valuation discounts.
- **Difficulty/feasibility/publication:** High / Medium / Private-credit valuation smoothing and public disclosure information lag.
- **24-month illustrative screening:** $190k hypothetical total 24-month labor/data/compute/compliance cost; rollout begins after 10 months; annual gross benefit scenarios $0k / $115k / $275k (downside/base/upside) for the remaining 1.1666666666666667 years. Net ROI=(benefit×active years−cost)/cost = -100.0% / -29.4% / 68.9%. These figures are scenario *assumptions*, not expected value, observed alpha, institutional revenue, or forward predictions.
- **Risk:** BDC portfolio company identities, valuation methods and distressed sales are not uniformly disclosed; matching bias.
- **Public source entry:** [SEC EDGAR API documentation](https://www.sec.gov/search-filings/edgar-application-programming-interfaces) · [SEC developer resources and disclosure revisions](https://www.sec.gov/search-filings/edgar-search-assistance/accessing-edgar-data); granular availability/licensing unverified.
- **Novelty vs archive:** Distinct from CMBS maturity/refinance hazard and TRACE ETF NAV stress: tests *BDC marked private loan holdings*.
- **Full agent/engineering files:** [idea folder](./17-us-bdc-private-credit-marks/README.md).

## 18. Wheat Export Inspection Revisions to Global Basis and Calendar Spreads — Domestic/Global Quant (priority 88/100)
- **Market / geography:** US, Black Sea and international wheat futures/physical flows.
- **Problem and decision:** Weekly port inspection momentum and monthly USDA supply tables arrive at different times and may contain meaningful revisions. **Decision:** Hedge wheat calendar spreads around official export inspection versus world balance-sheet information releases.
- **Falsifiable H1:** Vintage-corrected inspection surprises anticipate regional wheat basis and nearby-deferred spread movements beyond seasonality and WASDE.
- **Equation:** `BasisChange_{r,t+h}=alpha+beta*(InspectionsPublished_t-ExpectedInspections_t)+gamma*Weather_t+epsilon`. **Variable/constraint meanings:** r region; expected inspections estimated using only pre-release history; h is post-release decision horizon with realistic market access.
- **Data and granularity:** USDA AMS export grain inspections dashboard, USDA wheat supply/price tables, official crop calendars, futures curves and export policy announcement records. Grain: weekly USDA inspection release × grain class × destination × exchange quote timestamp.
- **Decision clock:** USDA dashboard launched Oct 14 2026 and wheat tables updated Nov 12 2026; do not replace historic reports with latest annual revisions.
- **Feasible baseline / candidate / advanced:** Monthly seasonal wheat spread regression using last known WASDE / Mixed-frequency distributed-lag export surprise model / Structural Bayesian crop-flow network with regional stock constraints and censoring.
- **Metrics:** spread forecast delta, regional basis tracking, net slippage-adjusted hedge P&L, regime robustness. **Explicit no-go:** No predictive improvement after weather, futures calendar effects and contemporaneous official release lags.
- **Execution/capacity:** CME wheat futures tick, spread roll, physical basis accessibility and region transport costs.
- **Difficulty/feasibility/publication:** High / Medium / Mixed-frequency official export releases and wheat basis transmission.
- **24-month illustrative screening:** $175k hypothetical total 24-month labor/data/compute/compliance cost; rollout begins after 9 months; annual gross benefit scenarios $0k / $100k / $265k (downside/base/upside) for the remaining 1.25 years. Net ROI=(benefit×active years−cost)/cost = -100.0% / -28.6% / 89.3%. These figures are scenario *assumptions*, not expected value, observed alpha, institutional revenue, or forward predictions.
- **Risk:** Weekly inspections differ from actual export commitments; Black Sea supply and policy announcements may dominate.
- **Public source entry:** [USDA grain export inspection dashboard announcement](https://www.ams.usda.gov/content/usda-launches-export-grain-inspection-dashboard) · [USDA ERS wheat supply/demand/price data](https://ers.usda.gov/data-products/wheat-data); granular availability/licensing unverified.
- **Novelty vs archive:** Unlike Australian water allocation/crop basis, uses multinational export timing, inspection vintages and wheat calendar spreads.
- **Full agent/engineering files:** [idea folder](./18-global-wheat-export-inspection-basis/README.md).

## 19. Canadian Mortgage Renewal Cohorts to Bank Credit-Risk Dispersion — Domestic/Global Quant (priority 87/100)
- **Market / geography:** Canadian banks, mortgage credit and bank equity/CDS.
- **Problem and decision:** Fixed-mortgage renewal resets vary across vintage cohorts, producing delayed stress without an immediate change in aggregate debt stock. **Decision:** Hedge Canadian bank credit/equity risk using public maturity-cohort mortgage renewal exposure rather than broad unemployment alone.
- **Falsifiable H1:** Estimated vintage-conditioned payment shock predicts cross-bank loan loss and valuation dispersion beyond level rates and employment controls.
- **Equation:** `Shock_{cohort,t}=Balance_{cohort}*max(RenewalPayment_t-OldPayment,0); ECL_{bank,t+h}=beta*Shock+controls`. **Variable/constraint meanings:** Balance is refinanceable exposure (public aggregate proxy initially), ECL expected credit loss; individual bank vintage mapping may be incomplete.
- **Data and granularity:** Bank of Canada public mortgage balances/rates, staff renewal methodology, bank annual/quarterly mortgage disclosures, CAD rate and housing data. Grain: Canadian mortgage cohort × monthly public release × bank quarterly filing.
- **Decision clock:** Use released monthly tables and historical market expectations before renewal; a 2025 note's projected 2026 payments are scenario assumptions, not observed outcomes.
- **Feasible baseline / candidate / advanced:** Bank loss sensitivity to national unemployment and policy rate alone / Vintage-cohort mortgage reset microsimulation from public aggregates / Hierarchical hazard model linking repricing, prepayment and issuer loan-level exposures.
- **Metrics:** future loss forecast gain, bank-spread risk hedging, sensitivity to vintage assumptions, net hedging cost. **Explicit no-go:** No cross-bank predictive signal after public loan books and unemployment/rate controls, or estimates too wide to act on.
- **Execution/capacity:** TSX bank/equity/CDS liquidity, CAD FX basis, sector beta hedges and credit market impact.
- **Difficulty/feasibility/publication:** Medium-high / High for aggregate stress, issuer value conditional / Mortgage maturity-vintage cohort stress versus bank heterogeneous ECL.
- **24-month illustrative screening:** $160k hypothetical total 24-month labor/data/compute/compliance cost; rollout begins after 8 months; annual gross benefit scenarios $0k / $105k / $240k (downside/base/upside) for the remaining 1.3333333333333333 years. Net ROI=(benefit×active years−cost)/cost = -100.0% / -12.5% / 100.0%. These figures are scenario *assumptions*, not expected value, observed alpha, institutional revenue, or forward predictions.
- **Risk:** Public aggregate cohorts do not identify each bank's borrower vintage distribution or underwriting quality.
- **Public source entry:** [Bank of Canada mortgage lending flows and balances](https://www.bankofcanada.ca/rates/banking-and-financial-statistics/funds-advanced-and-outstanding-balances-for-new-and-existing-lending-by-chartered-banks/) · [Bank of Canada staff note on mortgage renewal](https://www.bankofcanada.ca/2025/07/staff-analytical-note-2025-21/); granular availability/licensing unverified.
- **Novelty vs archive:** Compared with Korean household DSR, this is Canadian *mortgage fixed-rate renewal cohort repricing* versus bank credit loss forecasts.
- **Full agent/engineering files:** [idea folder](./19-canadian-mortgage-renewal-bank-risk/README.md).

## 20. Asia–US Cross-Listed ADR Opening Auction Information Transfer — Domestic/Global Quant (priority 86/100)
- **Market / geography:** US ADRs and Korea/Japan/Taiwan/Hong Kong local shares.
- **Problem and decision:** Local home-market closes and US ADR opening auctions occur asynchronously; simplistic close-to-open arbitrage ignores FX, share conversion and spreads. **Decision:** Choose hedge and execution timing for US ADR versus home-market overnight fair value.
- **Falsifiable H1:** An asynchronous local-information estimator reduces US ADR opening-price execution error beyond last local close plus FX conversion.
- **Equation:** `FairADR_{i,t}=Ratio_i*LocalPrice_{i,homeclose}*FX_{i,t}+CrossMarketNews_{i,t}`. **Variable/constraint meanings:** Ratio_i is point-in-time ADR share ratio, FX has correct currency direction, CrossMarketNews is post-local close information known before US auction.
- **Data and granularity:** Issuer depositary receipts ratios, local listings, public filings, FX quote timestamps, US ADR opening auctions, dividends and corporate action history. Grain: ADR × home-market session × US opening-auction timestamp.
- **Decision clock:** Prevent local-price forward fill across sessions; ratio/corporate actions must be known at the US quote decision time.
- **Feasible baseline / candidate / advanced:** Last home close × publicly known ADR conversion ratio × contemporaneous FX spot / State-space asynchronous Kalman fair-value update using futures and related peer prices / Continuous-time latent-price discovery with joint jump and optimal execution inventory control.
- **Metrics:** auction fair-value error, paired realized slippage, inventory risk, settlement/convertibility feasibility. **Explicit no-go:** No consistent opening execution improvement after financing, foreign exchange, depositary and auction spread costs.
- **Execution/capacity:** ADR opening auction depth, ADR conversion channel capacity, local/US holiday and FX hedging constraints.
- **Difficulty/feasibility/publication:** High / Medium / Asynchronous global price discovery with share-class conversion friction.
- **24-month illustrative screening:** $225k hypothetical total 24-month labor/data/compute/compliance cost; rollout begins after 10 months; annual gross benefit scenarios $0k / $120k / $310k (downside/base/upside) for the remaining 1.1666666666666667 years. Net ROI=(benefit×active years−cost)/cost = -100.0% / -37.8% / 60.7%. These figures are scenario *assumptions*, not expected value, observed alpha, institutional revenue, or forward predictions.
- **Risk:** ADR conversion fees, access restrictions, local holidays and stale home quotes create phantom arbitrage.
- **Public source entry:** [SEC developer resources and disclosure revisions](https://www.sec.gov/search-filings/edgar-search-assistance/accessing-edgar-data) · [SEC EDGAR API documentation](https://www.sec.gov/search-filings/edgar-application-programming-interfaces); granular availability/licensing unverified.
- **Novelty vs archive:** Prior global covariance regime and FX hedge programs forecast portfolio risk; this models cross-listed single-name auction lead-lag with depositary mechanics.
- **Full agent/engineering files:** [idea folder](./20-asia-us-adr-opening-price-discovery/README.md).


## Portfolio-wide interpretation
Value-for-money, operational resilience and risk monitoring should be compared within each economics unit, not collapsed into Sharpe alone. Risk/control benefits can be non-cash. Long/short or derivative experiments require transaction costs, historical feasible market access, post-release latency, realistic bid/ask, FX basis, cash financing and region-specific trading calendars. A negative or inconclusive outcome is a legitimate research result.

**Independent validation required:** available-at timestamps, vintage ledger, source permission, horizon purging, group-aware bootstraps, out-of-sample feasibility, multiple-test correction, break-even capacity and actual business owner approval. Favor standalone deterministic quality engines before allocating human time to speculative trading hypotheses.
