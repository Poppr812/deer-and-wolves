# Deer and Wolves

A predator-prey game based on a summer-camp field game, in a single HTML file
with no dependencies or build step. It runs on any phone, tablet, or computer
with a browser.

**Play:** open `index.html`, or the GitHub Pages link once it is enabled.

## How it plays

- 21 animals on a field: 18 deer, 3 wolves. An odd total so the sides never split evenly.
- Deer run from one side to the other. Wolves try to tag them — one catch per wolf per round.
- A tagged deer becomes a wolf. A wolf that catches nothing becomes a deer.
- The direction reverses each round, and the population swings: wolves boom,
  run out of deer, starve, and the deer come back.

The bars in the woods at each end are the point of the game: they show each
population's history and the band it keeps leaving and returning to —
dynamic equilibrium, without needing the term.

## Controls

| Action | Input |
|---|---|
| Steer | Drag (mouse or finger), or WASD / arrow keys |
| Start / next round | Space or Enter, or tap the prompt |
| Pause | P |
| Restart | R |
| Mute | M |

## Files

- `index.html` — the current game (v2.1)
- `RULES.md` — background, rules, design direction, and the plan for levels 2 and 3
- `versions/` — earlier frozen versions (v1.0, v2.0)
