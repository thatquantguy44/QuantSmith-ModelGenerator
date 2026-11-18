# Proposed runtime — Stock-Loan Repricing Bands with Relationship Friction

**NOT IMPLEMENTED.** This file is an executable architecture proposal. No package, executable module, entry point, service, backtest or production job is supplied or claimed by this batch.

## Future module boundaries

| Proposed module | Input | Output |
|---|---|---|
| `qmg.adapters.loan_repricing` | rights-approved source manifest | typed loan x repricing proposal/response event events |
| `qmg.point_in_time.asof` | events, decision clock | immutable available-at snapshot |
| `qmg.research.loan_repricing_inertia_bands.features` | snapshot | fee gap, duration in band, response propensity and net processing cost |
| `qmg.research.loan_repricing_inertia_bands.baseline` | features, costs, limits | baseline actions/forecasts |
| `qmg.research.loan_repricing_inertia_bands.candidate` | same inputs | hold/reprice recommendation, approved band and counterfactual uncertainty |
| `qmg.evaluation.walk_forward` | frozen splits and delayed outcomes | comparison, negatives and verdict |

## Future configuration contract

```yaml
idea_id: QMG-20261116-05
mode: public_research
adapter: loan_repricing
as_of_utc: REQUIRED_FROM_RUN
source_manifest: REQUIRED_REVIEWED_PATH_AND_HASH
cost_config: REQUIRED_MEASURED_OR_LABELED_SCENARIO
limits: REQUIRED_DOMAIN_APPROVED_LIMITS
seed: 20261116
allow_private_inputs: false
allow_live_orders: false
```

Illustrative **future** command, expected to fail today because no runtime exists:

```bash
python -m qmg.research.loan_repricing_inertia_bands.run --config reviewed-config.yaml --mode shadow
```

The intended CLI would return 0 only for a reproducible completed report, 2 for invalid arguments/units, 3 for rights/time/source blockers and 4 for infeasibility. These exit contracts are proposed, not tested. Persist hold/reprice recommendation, approved band and counterfactual uncertainty plus source/code/config/lock hashes, training dates, exclusions and actual timestamps. No outbound fee message; policy must provide an auditable reason and retain borrower/owner rights as hard constraints. Do not schedule this command until implementation and shadow gates pass.
