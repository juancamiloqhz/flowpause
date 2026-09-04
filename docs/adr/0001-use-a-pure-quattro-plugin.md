---
status: accepted
date: 2026-09-04
---

# Use a pure Omarchy Quattro plugin

FlowPause will begin as a pure Omarchy 4 / Quattro plugin: one resident service
owns scheduling and bounded state, one minimal bar widget exposes status and
immediate actions, and any panel or overlay loads only on demand. This was chosen
over a standalone application or plugin-plus-daemon design to reuse Omarchy's
native shell contracts and avoid another persistent runtime. The trade-off is a
shared failure domain with `omarchy-shell` and deliberate Omarchy platform
lock-in.

Do not add a helper daemon, second Quickshell process, web runtime, bundled
executable, or hybrid architecture unless a bounded experiment demonstrates a
required capability or isolation need and a later ADR accepts the additional
resource, packaging, security, and lifecycle costs.
