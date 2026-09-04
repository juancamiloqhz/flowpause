---
status: accepted
date: 2026-09-04
---

# Treat resource use and shell safety as release gates

Feature correctness alone is insufficient because FlowPause executes inside the
long-running `omarchy-shell` process. Every distributable build must satisfy the
controlled enabled-versus-disabled measurement, lifecycle, fail-open, privacy,
and bounded-state requirements in
[`docs/performance-contract.md`](../performance-contract.md). This deliberately
favours fewer context-sensitive features over polling, persistent helpers,
hidden rendering, invasive observation, or uncertain shell reliability.
