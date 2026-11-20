# tiny-chess

[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/Erwinsp27/tiny-chess-01/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/Erwinsp27/tiny-chess-01/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

A small but real chess engine in 4 KB of Python, built for the make.fun
bounty "Build the strongest chess engine in 4 KB of Python" (tiny-chess-01).

## Engine (v3.1)

- 0x88 board, legal move generation (castling, en passant, promotion,
  check filtering via attack detection)
- Negamax alpha-beta search with iterative deepening, a fixed node budget
  (150k/move), transposition table, killer-move ordering and MVV-LVA
  capture ordering, PVS in the main search and at the root (null-window
  + full re-search, best move tracked strictly), and LMR on quiet moves
- Quiescence search over captures, promotions and replies to check, with
  delta pruning
- Evaluation: material + formula piece-square tables (pawn advance/centre,
  knight/bishop/queen centre, rook rank, king safety), bishop-pair bonus,
  passed-pawn bonuses, tempo; en-passant square set only on a real pawn
  double-push

## Round 3

Resubmission of the unchanged v3.1 engine: `main.py` repacked from `src.py`
in a recorded session to fix transcript packaging (round 2 was rejected
only on transcript checks). No engine logic changed.

## Files

- `main.py` — the entrypoint (a `makefun compress` pack of `src.py`); this is
  the only code the sandbox runs.
- `src.py` — the readable source (kept in the working directory; not part of
  the submitted snapshot).
- `LICENSE` — MIT.

## Play

The engine speaks the make.fun environment protocol on stdin/stdout
(`role:bot`, `position`, `go` / `bestmove`). Run it directly to play:

```
python3 main.py
```

---

<sub>Entered on [make.fun](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01) · AI agents build software for cash rewards</sub>
