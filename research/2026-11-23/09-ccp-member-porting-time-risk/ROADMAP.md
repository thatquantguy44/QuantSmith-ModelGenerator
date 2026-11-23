# ROADMAP — CCP Member Default Position-Porting Time and Liquidity Optimization
**No implementation started. Milestones are planning assumptions, not commitments.**

## Phase 0: rights and science gate (weeks 1–2)
Check DTCC FICC Mortgage-Backed Securities Division, BIS Basel III Monitoring Release, Sep 23 2026 versus exact needed fields: Public CCP rulebooks; synthetic position/eligibility and margin profiles; simulated member outage. Verify calendar and rights. Reject unlicensed data.

## Phase 1: synthetic baseline (weeks 3–4)
Freeze math `min_{x_{ij}} Σ_{ij} x_{ij}*(PortDelay_{ij}+λ*MarginShortfall_{ij}) subject to Σ_j x_{ij}≤Position_i, K_j≥Σ_i x_{ij}`, create deterministic fixtures and implement `Manual first-available eligible clearing member routing`. Gate AC-001 and AC-002.

## Phase 2: measured prototype (weeks 5–8)
Try `Multi-period mixed-integer stochastic porting/survival flow simulator`, holdout on available historical timestamps and record Porting completion by deadline, unmet margin, loss given port failure, rerouting overhead; compare non-parametric alternative and no-action.

## Phase 3: controlled shadow replay (weeks 9–12, if feasible)
Test Actual CCP porting legality and bilateral customer consents unknown, correlated failures may be unidentifiable.; estimate actual execution Not a deployable CCP recovery plan; scenario policy must be vetted by legal and risk., then decide No improvement in adverse default scenarios over conservative porting alternatives or reliance on forbidden client position data..

## Phase 4: human decision
Independent quant/domain/legal reviewers validate. Annual benefit sensitivity $95k is **not** revenue; calculate business case only from audited data. Research can close as a negative result.
