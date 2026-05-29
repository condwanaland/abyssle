# Abyssle Testing Params

Dev mode is enabled with `?dev=1`. Without `dev=1`, testing params are ignored and the app uses normal production storage.

Dev mode uses isolated localStorage keys under `abyssle:dev:v1`, so test games do not affect your real streaks.

## Params

| Param | Example | Behavior |
| --- | --- | --- |
| `dev=1` | `index.html?dev=1` | Enables dev mode and shows the dev panel. |
| `date=YYYY-MM-DD` | `index.html?dev=1&date=2026-06-12` | Plays as if today is that local date. Invalid dates are ignored. |
| `answer=xxxxx` | `index.html?dev=1&answer=coral` | Forces any 5-letter answer. Non-letters or non-5-letter values are ignored. |
| `reset=day` | `index.html?dev=1&reset=day` | Clears the saved game for the active dev date only. |
| `reset=all` | `index.html?dev=1&reset=all` | Clears all dev-mode stats and dev-mode saved days. |

## Common URLs

```text
index.html?dev=1
index.html?dev=1&date=2026-06-12
index.html?dev=1&answer=coral
index.html?dev=1&date=2026-06-12
index.html?dev=1&date=2026-06-12&reset=day
index.html?dev=1&reset=all
```

## Notes

- `reset=day` and `reset=all` are one-shot actions. After running, the app removes `reset` from the URL when the browser allows it.
- Forced answers are useful for checking rare non-`abyss` days, duplicate-letter feedback, result text, and copy output.
- The dev panel includes quick links for previous day, next day, reset this day, reset dev stats, force `abyss`, force `coral`, and return to the generated answer.
