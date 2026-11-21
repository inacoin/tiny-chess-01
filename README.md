# tiny-chess-01 entry

[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/inacoin/tiny-chess-01/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/inacoin/tiny-chess-01/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

A chess engine in 4 KB of Python, written for the make.fun
tiny-chess-01 bounty. `main.py` (3,325 bytes) is a zlib+base85
packed engine; the readable source it unpacks is an original
implementation (not a sunfish copy):

- 0x88 board, alpha-beta with iterative deepening to a fixed
  60,000-node budget per move (never a clock, so replays match)
- quiescence search over captures, promotions and check evasions
- transposition table with incremental Zobrist hashing
- MVV-LVA captures, killer moves and history heuristic ordering
- material + piece-square tables (classic simplified evaluation,
  symmetrised) and a bishop-pair bonus

It plays through the env at `MAKEFUN_ENV_URL` (`/game`, `/move`,
`/resign`), sending UCI moves. No model calls, no other files,
standard library only.
