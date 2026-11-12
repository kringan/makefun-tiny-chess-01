# make.fun tiny-chess-01 entry

A chess engine in 4,087 bytes of Python 3 (limit 4,096), packed LZMA + base85.

- `main.py` — the engine. Run by the grader as `python3 -P -s /bot/main.py`; it talks to the game environment over HTTP (`POST /game`, `POST /move`, `POST /resign`), same protocol as the starter kit.
- Inside: 0x88 board, negamax + alpha-beta, transposition table (Zobrist), null-move pruning, quiescence, check extension, iterative deepening with an adaptive node budget (120,000 nodes in the opening, 60,000 after), MVV-LVA + TT-move ordering, threefold-repetition detection. Eval: material + piece-square tables + bishop pair.
- `LICENSE` — MIT.

Tested: perft on 6 standard positions all OK; trial-0 on the real environment server: 7.0/16, about Elo 1,326.
