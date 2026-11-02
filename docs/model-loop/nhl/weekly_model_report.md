# NHL engine weekly report

Generated 2026-11-02T20:54:34Z. Read only: it grades what the engine published before each game and changes no number. The engine's models are chosen by its own protocol (hockey/model/walkforward.js).

Served: **edgedesk_nhl_v1:xg_core** (validation 2026-10-29T13:26:41.104Z).

## Season to date and this week

| | n | Log loss | Brier | Accuracy | Priced home win | Home won | Total MAE | Margin MAE |
|---|---|---|---|---|---|---|---|---|
| Season to date | 142 | 0.6601 | 0.2340 | 0.5915 | 0.5329 | 0.5845 | 1.79 | — |
| Week 2026-10-26 to 2026-11-02 | 47 | 0.6469 | 0.2281 | 0.5957 | 0.5499 | 0.5106 | 1.89 | — |

## Against its own record

Season log loss 0.66013 on 142 games against 0.66286 on the confirmation 2021-2026 window (t = -0.2): **within what its out-of-sample record promised**.
Against a constant home-win rate of 0.5363: log loss difference -0.02336 (95% interval [-0.04712, 0.00102]), not yet distinguishable from it.

## Patterns

Moneyline: won minus priced, with z = (wins - sum of prices) / sqrt(sum p(1 - p)), the distance in the standard deviations the engine's own prices imply. Totals: actual minus expected, with a t. Flagged: n >= 30 and |z| or |t| >= 2.0. A flag is a research question for the engine's next protocol amendment, not a change.

| Pattern | Market | n | Residual | z / t | |
|---|---|---|---|---|---|
| all games | moneyline | 142 | 0.0516 | 1.25 z |  |
| all games | total | 142 | 0.2950 | 1.62 t |  |
| home favourite (p >= 0.60) | moneyline | 30 | 0.1609 | 1.84 z |  |
| home underdog (p <= 0.40) | moneyline | 7 | 0.2016 | 1.11 z |  |
| near a coin flip (0.40 < p < 0.60) | moneyline | 105 | 0.0104 | 0.21 z |  |
| home side on a back-to-back | moneyline | 5 | -0.1133 | -0.52 z |  |
| home side on a back-to-back | total | 5 | 1.5700 | 2.14 t |  |
| away side on a back-to-back | moneyline | 26 | 0.0482 | 0.50 z |  |
| away side on a back-to-back | total | 26 | 0.3920 | 1.09 t |  |
| goalie the price assumed: PROJECTED_LIKELY | moneyline | 3 | 0.0734 | 0.26 z |  |
| goalie the price assumed: PROJECTED_UNCERTAIN | moneyline | 139 | 0.0511 | 1.22 z |  |

## Data

261 ledger records over 175 games; 142 graded.
The graded games were priced by more than one model: edgedesk_nhl_v1:xg_core, edgedesk_nhl_v1:xg_no_goalie.

Changes: none: this report changes no number. NHL engine's models and hyperparameters are chosen by its own protocol (hockey/model/walkforward.js); a flagged pattern is a question for its next amendment.
