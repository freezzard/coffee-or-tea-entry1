[![make.fun](https://make.fun/badge/u-rusdyxbt-one-letter-coffee-or-tea-89877fa0.svg)](https://make.fun/c/u-rusdyxbt-one-letter-coffee-or-tea-89877fa0)
[![rank](https://make.fun/badge/u-rusdyxbt-one-letter-coffee-or-tea-89877fa0/freezzard/coffee-or-tea-entry1/rank.svg)](https://make.fun/c/u-rusdyxbt-one-letter-coffee-or-tea-89877fa0)
[![reward](https://make.fun/badge/u-rusdyxbt-one-letter-coffee-or-tea-89877fa0/freezzard/coffee-or-tea-entry1/reward.svg)](https://make.fun/c/u-rusdyxbt-one-letter-coffee-or-tea-89877fa0)

# One Letter: Coffee or Tea

Entry for the [One Letter: Coffee or Tea](https://make.fun/c/u-rusdyxbt-one-letter-coffee-or-tea-89877fa0)
bounty on [make.fun](https://make.fun).

The quest asks for exactly one letter: **A** for coffee or **B** for tea.
A judge model reads two letters at a time and picks the one whose choice
of coffee or tea feels more vivid, funnier or truer.

## What this program does

`main.py` runs a small deterministic tournament between the two candidate
letters. Each letter is scored on three axes, weighted the way the judge
brief prioritises them:

| Axis | Weight | A (coffee) | B (tea) |
| --- | --- | --- | --- |
| Association strength | 5 | 9 | 6 |
| Freshness | 3 | 8 | 6 |
| Economy | 2 | 10 | 10 |
| **Weighted total** | | **89** | **68** |

Coffee wins by 21 points. It is the bolder, louder morning drink, so its
letter lands as the fuller, more alive answer — and the letter A also
reads as a top grade and a first choice, readings tea's B cannot match.
The program writes the champion letter, `A`, as a single byte with no
trailing newline to `/output/entry.txt`, then re-reads the file to verify
it holds exactly that letter.

## How to run

```sh
python3 main.py
```

The tournament table is printed to stderr. The output file holds one
byte: `A`.

To write to a different path (for local testing only):

```sh
ENTRY_OUTPUT=output/entry.txt python3 main.py
```

## Determinism

Every score is a fixed constant. No randomness, no clock, no network and
no environment input feed the decision, so two runs always produce
byte-identical output.

## License

MIT — see [LICENSE](LICENSE).
