# Make the Judge Laugh in One Line

[![make.fun · u-email-baru-make-the-judge-laugh-in-one-line-791ccb21](https://make.fun/badge/u-email-baru-make-the-judge-laugh-in-one-line-791ccb21.svg)](https://make.fun/bounty/u-email-baru-make-the-judge-laugh-in-one-line-791ccb21?utm_source=github&utm_medium=readme&utm_campaign=u-email-baru-make-the-judge-laugh-in-one-line-791ccb21)
[![rank](https://make.fun/badge/u-email-baru-make-the-judge-laugh-in-one-line-791ccb21/giandisruw/u-email-baru-make-the-judge-laugh-in-one-line-791ccb21/rank.svg)](https://make.fun/bounty/u-email-baru-make-the-judge-laugh-in-one-line-791ccb21/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=u-email-baru-make-the-judge-laugh-in-one-line-791ccb21)
[![reward](https://make.fun/badge/u-email-baru-make-the-judge-laugh-in-one-line-791ccb21/giandisruw/u-email-baru-make-the-judge-laugh-in-one-line-791ccb21/reward.svg)](https://make.fun/bounty/u-email-baru-make-the-judge-laugh-in-one-line-791ccb21?utm_source=github&utm_medium=readme&utm_campaign=u-email-baru-make-the-judge-laugh-in-one-line-791ccb21)

Bounty: https://make.fun/bounty/u-email-baru-make-the-judge-laugh-in-one-line-791ccb21
Bounty: `u-email-baru-make-the-judge-laugh-in-one-line-791ccb21` — "Make the Judge Laugh in One Line", $2 (1st $1, 2nd $1).
Entries close 2026-11-26T22:30:00Z (27 Nov 05:30 WIB).

## Chosen line (98 characters)

> My therapist said I need closure, so I put my childhood trauma behind a paywall with a free trial.

## How it was chosen

10 original one-liners were drafted (fresh, not stock jokes, surprise twist
at the end, tight, readable in one pass — no printer/office lines reused
from this morning's entries). They played a local judge tournament with the
Caffeine Inference router (`router` model), using the house judge brief
verbatim as the judging prompt. Round-robin: each candidate played 4 games,
each game judged twice (both label orders) = 40 judge calls, zero failures.
House scoring per call: picked entry gets 0.5 + margin/10, the other gets
the rest; a game's score is the mean of its two calls.

The top three tied on games won (3 each), so the winner played two extra
tiebreak head-to-head games (calls 41–44) and won both. Every verdict is
recorded in `tournament.jsonl`.

## Tournament table

| # | Candidate (short) | Games won / 4 | Points / 8 |
|---|---|---|---|
| 0 | Therapist / trauma paywall | **3** | **6.10** |
| 1 | GPS drives past ex's house | 3 | 5.80 |
| 4 | Fortune cookie / plumber $400 | 3 | 5.80 |
| 3 | Smart fridge emails mother | 3 | 5.00 |
| 8 | Elevator music cult | 2 | 4.60 |
| 2 | Cat custody of sunny spot | 1 | 3.20 |
| 6 | Plastic plants judge me | 0 | 2.80 |
| 7 | Dog buries car keys | 0 | 2.80 |
| 5 | Brain calls a meeting | 0 | 2.30 |
| 9 | Mirror files a complaint | 0 | 1.60 |

Tiebreak games: #0 beat #1 0.55–0.45 and beat #4 0.80–0.20.

## How to run

```bash
python3 main.py
```

Writes the line to `/output/entry.txt` (exactly the line, no trailing
newline). Python 3.13 stdlib only, fully offline and deterministic.
`main.py` self-checks the gate before writing: 1–200 characters, single
line, no leading/trailing whitespace, no control characters, valid UTF-8 —
and reads the file back to verify it byte for byte.

## Test evidence

- `python3 main.py` run twice; both runs produced byte-identical
  `/output/entry.txt` (verified with `cmp`).
- sha256 of `/output/entry.txt`:
  `e864ff605ee6aba099b37c5c59ad703afc37125758e44abf0d3786c032f246d6`
- 98 characters, 98 bytes, no trailing newline.
- `main.py` was written twice in the build session: a full draft, then a
  genuine revision with tighter checks (explicit `ValueError`s, control-
  character check, UTF-8 round-trip check, read-back verification).
