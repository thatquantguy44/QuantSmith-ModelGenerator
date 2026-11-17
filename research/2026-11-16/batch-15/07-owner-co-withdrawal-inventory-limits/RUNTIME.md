# Proposed runtime — Owner Co-Withdrawal Limits for Lendable Inventory

**NOT IMPLEMENTED.** This file is an executable architecture proposal. No package, executable module, entry point, service, backtest or production job is supplied or claimed by this batch.

## Future module boundaries

| Proposed module | Input | Output |
|---|---|---|
| `qmg.adapters.owner_inventory` | rights-approved source manifest | typed owner x security x dated available-inventory snapshot events |
| `qmg.point_in_time.asof` | events, decision clock | immutable available-at snapshot |
| `qmg.research.owner_co_withdrawal_inventory_limits.features` | snapshot | common withdrawal factor, owner lineage groups and replacement tail scenarios |
| `qmg.research.owner_co_withdrawal_inventory_limits.baseline` | features, costs, limits | baseline actions/forecasts |
| `qmg.research.owner_co_withdrawal_inventory_limits.candidate` | same inputs | source concentration limits and joint-withdrawal stress certificate |
| `qmg.evaluation.walk_forward` | frozen splits and delayed outcomes | comparison, negatives and verdict |

## Future configuration contract

```yaml
idea_id: QMG-20261116-07
mode: public_research
adapter: owner_inventory
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
python -m qmg.research.owner_co_withdrawal_inventory_limits.run --config reviewed-config.yaml --mode shadow
```

The intended CLI would return 0 only for a reproducible completed report, 2 for invalid arguments/units, 3 for rights/time/source blockers and 4 for infeasibility. These exit contracts are proposed, not tested. Persist source concentration limits and joint-withdrawal stress certificate plus source/code/config/lock hashes, training dates, exclusions and actual timestamps. No raw owner identity or positions in public artifacts; a private run must use pseudonymous IDs and lineage access controls. Do not schedule this command until implementation and shadow gates pass.
