# tiny-chess-01 entry

[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/yz6941031-collab/tiny-chess-01/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/yz6941031-collab/tiny-chess-01/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

A compact chess engine in Python (0x88 board, alpha-beta search,
quiescence, transposition table, piece-square evaluation), built for
the [make.fun bounty tiny-chess-01](https://make.fun/bounty/tiny-chess-01).
Deterministic: fixed node budget, no clock.

Run: `MAKEFUN_ENV_URL=<env url> python3 main.py`

## Engine notes

- Search: negamax alpha-beta with iterative deepening under a fixed
  55,000-node budget (no wall clock, so trials replay byte-for-byte),
  quiescence over captures, promotions and check evasions, null-move
  pruning, late-move reductions and futility/delta pruning.
- Evaluation: incremental tapered material + piece-square tables with
  a bishop-pair bonus, maintained exactly through make/unmake.
- The 4,061-byte `main.py` is the make.fun-compressed form of the
  readable source it was packed from.
- Local practice gauntlet (6 house engines, depth-2 to 500k nodes):
  8 wins, 2 draws, 2 losses over 12 games, practice Elo 1545 against
  a 1,154 qualifying floor.
