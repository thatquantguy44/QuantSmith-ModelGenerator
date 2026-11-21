# PLAN — Evergreen Repo Early-Termination Optionality Risk Budget
**Architecture:** public/approved adapters → versioned temporal contract → eligibility gate → costed baseline → Least-squares Monte Carlo for bilateral asymmetric stop decisions → causal/economic replay → human review.

## Source ingestion and data shape
Synthetic open-repo terms, public SOFR and OFR repo curve history, legally enforceable reset/termination terms and funding costs.
Event key: contract × notice period × funding day × interest-rate state. Record original filing/publication alongside first local actionable market clock. Public repo rates have release lags; exact contract termination rights must be known at contract initiation, not retrofitted.
Integrate publicly identified records only after separate terms-of-use and granularity checks. Private data stay in private approved runtime.

## Implementable modules (proposed)
1. `contracts.py`: pydantic models for contract × notice period × funding day × interest-rate state and immutable timestamps.
2. `sources.py`: rights-aware loader of ofrrepo, secclose official references and separately licensed feeds.
3. `baseline.py`: Static repo spread plus deterministic notice-day funding reserve; must share opportunity universe and constraints with candidate.
4. `candidate.py`: Least-squares Monte Carlo for bilateral asymmetric stop decisions; add Nonzero-sum stochastic game with liquidity-dependent termination intensities only after ablation warrants complexity.
5. `feasibility.py`: exercise and continuation are contract-party-specific; funder and borrower exercise incentives must be separately simulated.
6. `evaluation.py`: metrics replacement funding loss, option premium calibration, cash-flow stress, tail liquidity gap, placebo, uncertainty and matched no-action baseline.
7. `report.py`: provenance and decision cost without asserting measured profitability.

## Identification challenges and alternatives
Non-observed counterparty exercise behavior; public term repo alone does not identify proprietary notice clauses. Use preregistered holdout splits, minimum economic materiality and delay-stressed baselines.
**Falsify:** Option charge unstable or no improvement over conservative notice reserve in stress holdouts.

## Delivery and rollback
Synthetic deterministic tests → available-at real-data audit → walk-forward/paired counterfactual → read-only shadow mode → human approval. Disable candidate on missing rights/clock or limit violation and revert to baseline. No code exists yet.
