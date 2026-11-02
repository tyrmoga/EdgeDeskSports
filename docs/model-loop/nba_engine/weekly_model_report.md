# NBA engine weekly report

Generated 2026-11-02T20:54:34Z. Read only: it grades what the engine published before each game and changes no number. The engine's models are chosen by its own protocol (nba/model/walkforward.js).

Served: **E_ridge_P** (validation 2026-10-28T18:57:44.496Z).

## Season to date and this week

| | n | Log loss | Brier | Accuracy | Priced home win | Home won | Total MAE | Margin MAE |
|---|---|---|---|---|---|---|---|---|
| Season to date | 92 | 0.6198 | 0.2166 | 0.6739 | 0.5409 | 0.5217 | 15.67 | 12.11 |
| Week 2026-10-26 to 2026-11-02 | 49 | 0.6139 | 0.2144 | 0.6939 | 0.5424 | 0.5714 | 16.90 | 11.97 |

## Against its own record

Season log loss 0.61979 on 92 games against 0.61681 on the test 2018-2026 window (t = 0.09): **within what its out-of-sample record promised**.
Against a constant home-win rate of 0.5612: log loss difference -0.07556 (95% interval [-0.1431, -0.00888]), it beats it.

## Patterns

Moneyline: won minus priced, with z = (wins - sum of prices) / sqrt(sum p(1 - p)), the distance in the standard deviations the engine's own prices imply. Totals: actual minus expected, with a t. Flagged: n >= 30 and |z| or |t| >= 2.0. A flag is a research question for the engine's next protocol amendment, not a change.

| Pattern | Market | n | Residual | z / t | |
|---|---|---|---|---|---|
| all games | moneyline | 92 | -0.0192 | -0.39 z |  |
| all games | total | 92 | 0.4710 | 0.23 t |  |
| home favourite (p >= 0.60) | moneyline | 33 | -0.0636 | -0.83 z |  |
| home underdog (p <= 0.40) | moneyline | 21 | -0.0111 | -0.11 z |  |
| near a coin flip (0.40 < p < 0.60) | moneyline | 38 | 0.0149 | 0.18 z |  |
| home side on a back-to-back | moneyline | 14 | -0.0443 | -0.35 z |  |
| home side on a back-to-back | total | 14 | 0.6770 | 0.13 t |  |
| away side on a back-to-back | moneyline | 16 | -0.0394 | -0.34 z |  |
| away side on a back-to-back | total | 16 | 4.6510 | 0.86 t |  |
| rotation stale: False | moneyline | 76 | -0.0398 | -0.75 z |  |
| rotation stale: True | moneyline | 16 | 0.0789 | 0.67 z |  |

## Data

616 ledger records over 121 games; 92 graded.
The graded games were priced by more than one model: edgedesk_nba_v1:E_ridge_P, edgedesk_nba_v1:G_stack_P.

Changes: none: this report changes no number. NBA engine's models and hyperparameters are chosen by its own protocol (nba/model/walkforward.js); a flagged pattern is a question for its next amendment.
