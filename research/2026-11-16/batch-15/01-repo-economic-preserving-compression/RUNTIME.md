# Proposed runtime — Repo Compression with Cash-Flow Preservation

**NOT IMPLEMENTED.** This file is an executable architecture proposal. No package, executable module, entry point, service, backtest or production job is supplied or claimed by this batch.

## Future module boundaries

| Proposed module | Input | Output |
|---|---|---|
| `qmg.adapters.repo_ledger` | rights-approved source manifest | typed repo ticket and dated cash/security obligation events |
| `qmg.point_in_time.asof` | events, decision clock | immutable available-at snapshot |
| `qmg.research.repo_economic_preserving_compression.features` | snapshot | dated incidence matrices, lot constraints and consent mask |
| `qmg.research.repo_economic_preserving_compression.baseline` | features, costs, limits | baseline actions/forecasts |
| `qmg.research.repo_economic_preserving_compression.candidate` | same inputs | proposed tear-up/resizing schedule, exact flow certificate and rejected-action reasons |
| `qmg.evaluation.walk_forward` | frozen splits and delayed outcomes | comparison, negatives and verdict |

## Future configuration contract

```yaml
idea_id: QMG-20261116-01
mode: public_research
adapter: repo_ledger
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
python -m qmg.research.repo_economic_preserving_compression.run --config reviewed-config.yaml --mode shadow
```

The intended CLI would return 0 only for a reproducible completed report, 2 for invalid arguments/units, 3 for rights/time/source blockers and 4 for infeasibility. These exit contracts are proposed, not tested. Persist proposed tear-up/resizing schedule, exact flow certificate and rejected-action reasons plus source/code/config/lock hashes, training dates, exclusions and actual timestamps. For a proposed 5,000-ticket set, target p95 solve time <=60 seconds and exact conservation certificate; infeasible or timed-out solves return original book. Do not schedule this command until implementation and shadow gates pass.
