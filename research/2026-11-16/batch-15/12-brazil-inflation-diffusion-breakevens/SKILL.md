---
name: research-brazil-inflation-diffusion-breakevens
description: Design or evaluate brazil inflation diffusion versus breakeven carry for Brazil; local nominal and inflation-linked government bonds; use for the stated economic decision, point-in-time data audit, baseline challenge and falsification gates. Research workflow only; not a deployed runtime.
---

# Research Brazil Inflation Diffusion versus Breakeven Carry

1. State the decision: Choose a DV01-neutral nominal-versus-inflation-linked bond overlay using released inflation breadth and survey dispersion. Read SPEC for `QMG-20261116-12` requirements and EVALS for the frozen gate before selecting a model.
2. Resolve public sources in SOURCES first. Use inflation release x survey public version x matched bond pair; reject unlicensed payloads and missing publication times. Preserve observed, published, received, available and effective times separately.
3. Align inputs to this clock: Trade no earlier than next Sao Paulo session after verified inflation and survey publication, with one-hour processing lag. Survey collection dates are never treated as public timestamps. Build released inflation diffusion, survey dispersion and known indexation carry. Keep future outcomes and later amendments out of features.
4. Reproduce the baseline: Carry/roll plus headline inflation surprise using a fixed ridge regression and identical risk budget. Match risk, costs, sample, execution clock and permitted actions before testing Sparse distributed-lag regression with local-projection diagnostics.
5. Run the domain negative test: Set nominal and linked yields to parallel shifts with no inflation shock: residual P&L must reflect declared duration mismatch, not be mislabeled inflation alpha. Stop on any future-data acceptance or hard-constraint violation.
6. Challenge the hypothesis: Inflation-breadth revisions and Focus dispersion improve next-quarter breakeven return forecasts by at least 10% squared-error reduction versus carry plus headline surprise, and add 20 annualized net bps at fixed risk. Apply exactly: GO if >=10% forecast MSE improvement and >=20 net annualized bps at unchanged risk with >=40 nonoverlapping quarterly outcomes; STOP if official component vintage or executable curve history cannot be established. Report all failed variants and effective independent sample size.
7. Review Illustrative $40m duration-matched overlay; constrain pair DV01 and <=1% of observed issue turnover. Local liquidity, BRL hedging, indexation and applicable taxes must be priced before investment use. Recompute the purely illustrative ROI using measured cost evidence if available; otherwise retain the assumption label and negative scenarios.
8. Return breakeven forecast, DV01 hedge and market-access gate, uncertainty, source lineage and a GO/STOP/BLOCKED verdict. Escalate Overlapping quarterly labels create false sample size; inflation indexation/tax rules and market-access costs can erase apparent returns. No current Brazilian tax recommendation is assumed. Never trade, change contracts, deploy or claim empirical completion from this document alone.

Use PLAN for adapter boundaries and TASKS for traceability; retain immutable manifests and dependency locks when implementation is later authorized. This repository workflow is not installed as a personal ChatGPT skill.
