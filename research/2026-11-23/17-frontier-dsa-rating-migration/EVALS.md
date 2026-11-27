# EVALS — Sovereign DSA Rating Migration Event Pricing for Frontier Bonds
**No empirical test run. Evaluation design, not evidence.**

## H1/H0 and economics
H1: First-public DSA risk-rating changes improve post-publication sovereign credit-loss calibration versus debt/GDP screens.
H0: the feasible `Latest public debt-to-GDP and reserves ratio` benchmark is not improved net of risk/cost.
Candidate: `Multi-state ordinal risk migration model with publication-aligned survival validation`. Advanced: Bayesian sovereign hazard with IMF policy intervention and restructuring recovery scenarios
Metrics: Default Brier score, out-of-time risk precision, spread change, no-trade capacity flags.

## Mandatory synthetic invariants
- `available_at_utc <= decision_time`, calendar/session alignment and source-version hash.
- Feasible decision constraints match: Pr(Default_{c,t+h}=1)=logit^{-1}(α+β*DSAChange_{c,t}+γ'ExternalDebt_{c,t}); EL=PD*LGD*EAD.
- Units and payable/receivable cash direction from: c country, DSAChange categorical first-public change, PD conditional default risk, LGD stressed recovery.
- True negative controls: DSA coverage selection and program endogeneity, non-tradable distressed bonds, rare default events.
- Equal event/asset universe, quoted bid/ask, capacity and no-action alternatives.

## Empirical design if licensed data eventually approved
Time-blocked train/validation/holdout, embargo overlaps and original-vintage release lags. Conduct matched policy replay, bootstrap by independent event block, monitor false discoveries across multiple choices, expose failed dates and liquidity drawdowns.
**Stop:** No improvement over conservative sovereign ratings baseline, or price move entirely before public timestamp..

## Cost and publication
Frontier bond sizes/spreads can defeat excess returns; focus risk-control research first.
$175k assumed total 24m development/data/maintenance cost; assumed launch in month 9; assumed annual gross outcome downside/base/upside $0k/$85k/$270k. Resulting 24m net ROI **-100.0% / -39.3% / 92.9% (downside/base/upside)**. These are invented transparent sensitivity inputs, not measured ROI, P&L, or investment advice.
Public papers and official datasets are context only, not replication. Any material positive result requires independently reproduced code + signed human review; no automatic trading.

## Acceptance gating
AC-001..AC-005 from SPEC each requires a runnable test record and model/data rights signoff. If source is incomplete, report a negative or blocked result, not a proxy alpha claim.
