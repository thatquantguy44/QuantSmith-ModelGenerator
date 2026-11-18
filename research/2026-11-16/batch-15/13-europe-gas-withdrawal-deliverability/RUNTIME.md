# Proposed runtime — European Gas Storage Deliverability Hedge

**NOT IMPLEMENTED.** This file is an executable architecture proposal. No package, executable module, entry point, service, backtest or production job is supplied or claimed by this batch.

## Future module boundaries

| Proposed module | Input | Output |
|---|---|---|
| `qmg.adapters.europe_gas_storage` | rights-approved source manifest | typed storage facility x gas day x publication version events |
| `qmg.point_in_time.asof` | events, decision clock | immutable available-at snapshot |
| `qmg.research.europe_gas_withdrawal_deliverability.features` | snapshot | withdrawal headroom, gas-day inventory state and hub connectivity |
| `qmg.research.europe_gas_withdrawal_deliverability.baseline` | features, costs, limits | baseline actions/forecasts |
| `qmg.research.europe_gas_withdrawal_deliverability.candidate` | same inputs | deliverability risk index and constrained seasonal hedge weights |
| `qmg.evaluation.walk_forward` | frozen splits and delayed outcomes | comparison, negatives and verdict |

## Future configuration contract

```yaml
idea_id: QMG-20261116-13
mode: public_research
adapter: europe_gas_storage
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
python -m qmg.research.europe_gas_withdrawal_deliverability.run --config reviewed-config.yaml --mode shadow
```

The intended CLI would return 0 only for a reproducible completed report, 2 for invalid arguments/units, 3 for rights/time/source blockers and 4 for infeasibility. These exit contracts are proposed, not tested. Persist deliverability risk index and constrained seasonal hedge weights plus source/code/config/lock hashes, training dates, exclusions and actual timestamps. Use gas-day definitions and MWh conversion consistently; data-quality flags propagate to bounds instead of becoming zero inventory. Do not schedule this command until implementation and shadow gates pass.
