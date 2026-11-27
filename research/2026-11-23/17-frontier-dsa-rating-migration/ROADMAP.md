# ROADMAP — Sovereign DSA Rating Migration Event Pricing for Frontier Bonds
**No implementation started. Milestones are planning assumptions, not commitments.**

## Phase 0: rights and science gate (weeks 1–2)
Check IMF Sovereign Risk/DSA Publications, World Bank Public DSA Country Repository versus exact needed fields: Country IMF/World Bank public DSA documents, sovereign events, IMF debt statistics, bond quotes and GDP vintages. Verify calendar and rights. Reject unlicensed data.

## Phase 1: synthetic baseline (weeks 3–4)
Freeze math `Pr(Default_{c,t+h}=1)=logit^{-1}(α+β*DSAChange_{c,t}+γ'ExternalDebt_{c,t}); EL=PD*LGD*EAD`, create deterministic fixtures and implement `Latest public debt-to-GDP and reserves ratio`. Gate AC-001 and AC-002.

## Phase 2: measured prototype (weeks 5–8)
Try `Multi-state ordinal risk migration model with publication-aligned survival validation`, holdout on available historical timestamps and record Default Brier score, out-of-time risk precision, spread change, no-trade capacity flags; compare non-parametric alternative and no-action.

## Phase 3: controlled shadow replay (weeks 9–12, if feasible)
Test DSA coverage selection and program endogeneity, non-tradable distressed bonds, rare default events.; estimate actual execution Frontier bond sizes/spreads can defeat excess returns; focus risk-control research first., then decide No improvement over conservative sovereign ratings baseline, or price move entirely before public timestamp..

## Phase 4: human decision
Independent quant/domain/legal reviewers validate. Annual benefit sensitivity $85k is **not** revenue; calculate business case only from audited data. Research can close as a negative result.
