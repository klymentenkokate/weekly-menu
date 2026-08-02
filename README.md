# Weekly menu

A pescatarian week planner built around one rule: **cook dinner once, eat it twice.**
Every dinner is made at double quantity and becomes the next day's lunch, so a week
takes fourteen cooking sessions rather than twenty-one.

77 recipes, all from what's on the shelf at [Mercadona](https://tienda.mercadona.es),
all under twenty minutes, all clearing 30 g of protein.

## What it does

- **Shuffle** rebuilds the week under every constraint at once
- **Favourites** (★ / less often) bias what the shuffle picks
- **Shopping list** totals every ingredient across the week, doubled for dinners, grouped by aisle
- **English / Українська** switcher — Spanish shelf names stay Spanish, because that's
  what the Mercadona app searches on

## Constraints enforced in code

| Rule | How |
|---|---|
| No protein source three days running | 9 sources tracked; because a dinner also fills the next day's lunch, same-protein dinners are kept ≥3 days apart |
| Max 2 whole eggs a day | Counted across breakfast + carried lunch + dinner |
| Every meal ≥30 g protein, ≤20 min | Validated across the whole library |
| Days land on an energy target | Lunch and dinner are locked together, so breakfast is the lever the solver uses |
| Only dinners that keep overnight get doubled | Shellfish, raw tartare and griddled dishes stay browsable but out of rotation |

Single self-contained HTML file — no build step, no dependencies, no external requests.

Set your own energy level in the browser console:

```js
localStorage.setItem('menuKcal', 1500)
```
