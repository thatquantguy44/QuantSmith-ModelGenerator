# Proposed runtime — Securities-Loan Dust-Lot Consolidation

**NOT IMPLEMENTED.** This file is an executable architecture proposal. No package, executable module, entry point, service, backtest or production job is supplied or claimed by this batch.

## Future module boundaries

| Proposed module | Input | Output |
|---|---|---|
| `qmg.adapters.loan_lots` | rights-approved source manifest | typed owner x borrower x security loan lot x service day events |
| `qmg.point_in_time.asof` | events, decision clock | immutable available-at snapshot |
| `qmg.research.securities_loan_dust_lot_consolidation.features` | snapshot | fixed servicing charge, permitted owner-lot map and movement-cost matrix |
| `qmg.research.securities_loan_dust_lot_consolidation.baseline` | features, costs, limits | baseline actions/forecasts |
| `qmg.research.securities_loan_dust_lot_consolidation.candidate` | same inputs | consolidation suggestions with per-owner exposure/revenue reconciliation |
| `qmg.evaluation.walk_forward` | frozen splits and delayed outcomes | comparison, negatives and verdict |

## Future configuration contract

```yaml
idea_id: QMG-20261116-10
mode: public_research
adapter: loan_lots
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
python -m qmg.research.securities_loan_dust_lot_consolidation.run --config reviewed-config.yaml --mode shadow
```

The intended CLI would return 0 only for a reproducible completed report, 2 for invalid arguments/units, 3 for rights/time/source blockers and 4 for infeasibility. These exit contracts are proposed, not tested. Persist consolidation suggestions with per-owner exposure/revenue reconciliation plus source/code/config/lock hashes, training dates, exclusions and actual timestamps. Deterministic tie-breaking and original-book fallback on infeasibility; quantity and owner revenue reconcile exactly to declared permitted changes. Do not schedule this command until implementation and shadow gates pass.
