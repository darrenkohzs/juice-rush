# Juice Rush

Single-file browser game (`index.html`): a fruit auto-runner with kitchen-themed obstacles.

## Level rules
- Every level is named after a fruit, in alphabetical order: Apple (1), Banana (2), then C…, D…, and so on.
- Difficulty must rise from A to Z: each new level should be harder than the one before.
- Levels live in the `LEVELS` array in `index.html`; add new ones at the end so the order stays alphabetical.
- Before shipping a level change, check it can be beaten with the in-page solver (it uses `JR.useLevel(i)` and `JR.simStep`): every required jump window should stay at least ~1.3 tiles (≈130 ms at 100% speed).
