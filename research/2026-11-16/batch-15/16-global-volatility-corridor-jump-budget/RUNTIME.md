# Proposed runtime — US–Europe Corridor Variance and Jump-Risk Budget

**NOT IMPLEMENTED.** This file is an executable architecture proposal. No package, executable module, entry point, service, backtest or production job is supplied or claimed by this batch.

## Future module boundaries

| Proposed module | Input | Output |
|---|---|---|
| `qmg.adapters.global_option_chains` | rights-approved source manifest | typed market x option expiry/strike x quote instant plus intraday underlying bars events |
| `qmg.point_in_time.asof` | events, decision clock | immutable available-at snapshot |
| `qmg.research.global_volatility_corridor_jump_budget.features` | snapshot | corridor variance, overnight jump proxies, executable strip costs and tail hedge Greeks |
| `qmg.research.global_volatility_corridor_jump_budget.baseline` | features, costs, limits | baseline actions/forecasts |
| `qmg.research.global_volatility_corridor_jump_budget.candidate` | same inputs | vega allocation, explicit option-strip positions and stress funding requirements |
| `qmg.evaluation.walk_forward` | frozen splits and delayed outcomes | comparison, negatives and verdict |

## Future configuration contract

```yaml
idea_id: QMG-20261116-16
mode: public_research
adapter: global_option_chains
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
python -m qmg.research.global_volatility_corridor_jump_budget.run --config reviewed-config.yaml --mode shadow
```

The intended CLI would return 0 only for a reproducible completed report, 2 for invalid arguments/units, 3 for rights/time/source blockers and 4 for infeasibility. These exit contracts are proposed, not tested. Persist vega allocation, explicit option-strip positions and stress funding requirements plus source/code/config/lock hashes, training dates, exclusions and actual timestamps. Reject crossed/stale quotes and impossible option monotonicity; no interpolation may create executable liquidity that was not quoted. Do not schedule this command until implementation and shadow gates pass.
