# Juice Rush

Single-file browser game (`index.html`): a fruit auto-runner with kitchen-themed obstacles.

## Level rules
- Every level is named after a fruit, in alphabetical order: Apple (1), Banana (2), then C…, D…, and so on.
- Difficulty must rise from A to Z: each new level should be harder than the one before.
- Levels live in the `LEVELS` array in `index.html`; add new ones at the end so the order stays alphabetical.
- Current levels: Apple (Easy), Banana (Hard: hanging cupboards with knives above and below), Cherry (Expert: turns into a spaceship mid-level via `PORTAL(x, "ship")` / `PORTAL(x, "cube")`).
- In ship mode holding the button makes the ship rise and releasing lets it fall; it can't rise above the portal's `ceil` (default 6.5) and can rest on the floor. The solver's state key must include `ship` and `portals`.
- Second life: the first hit bursts the fruit into a smaller seed (hitbox `SEED`, briefly invulnerable) that keeps running with the same jump/ship rules; a hit on the seed restarts the attempt. Levels must still be beatable without the seed, so the solver should treat a burst (`EV_BURST`) as a death.
- Before shipping a level change, check it can be beaten with the in-page solver (it uses `JR.useLevel(i)` and `JR.simStep`): every required jump window should stay at least ~1.3 tiles (≈130 ms at 100% speed).
