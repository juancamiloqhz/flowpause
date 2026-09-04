# FlowPause Product Repository

## Purpose

This public repository owns the FlowPause Omarchy plugin, its tests, implementation documentation, and release material. FlowPause is a respectful, lightweight break companion for Omarchy 4 / Quattro. Its permanent plugin ID is `io.github.juancamiloqhz.flowpause`.

## Public boundary

- Keep this repository self-contained and safe for public release.
- Never add private product strategy, raw research, participant or customer information, credentials, internal operations, or unpublished business material.
- Do not imply that FlowPause is an official Omarchy product or endorsed by Omarchy.
- Do not make medical, injury-prevention, focus-improvement, or productivity claims without product-specific evidence and explicit approval.

## Architecture constraints

- Begin as a pure Omarchy Quattro QML plugin: one singleton `service`, one minimal `bar-widget`, and on-demand panel or overlay UI only when required.
- Do not add a persistent helper daemon, second Quickshell process, webview, Electron runtime, account, network service, telemetry, runtime-downloaded code, install hook, `sudo`, or configuration overwrite without an explicit architecture decision.
- Use one canonical scheduler regardless of monitor count. Represent schedule state with absolute deadlines and reconcile it after shell restart, suspend/resume, lock/unlock, and delayed execution.
- Prefer documented, event-driven Omarchy, Quickshell, Hyprland, and Wayland signals. Do not poll shell commands or spawn periodic subprocesses in steady state.
- Keep persistence local, small, bounded, and limited to meaningful transitions. Never write countdown ticks or collect window titles, URLs, typed content, screenshots, or unrelated activity data.
- Hidden UI must not animate or repaint continuously. Load expensive surfaces only while visible and release them when closed.
- Fail open: FlowPause must never trap input, create duplicate prompts across monitors, or destabilize the shell.

## Product behavior

- Respect attention, protect autonomy, and never block the screen by default.
- Keep take, snooze, skip, pause, and resume actions obvious and immediately available.
- Reconcile idle/time-away state before showing an overdue prompt.
- Use calm, neutral language without guilt, streak pressure, or punishment.
- Follow Omarchy semantic theme tokens and keyboard interaction patterns; include accessible semantics, contrast, focus behavior, and reduced-motion handling in acceptance checks.

## Development workflow

- Develop against a pinned current Omarchy 4 / Quattro environment in a user-owned plugin checkout; never edit packaged files under `$OMARCHY_PATH`.
- Before changing host integration, read the current [Omarchy plugin development guide](https://plugins.omarchy.org/develop.html) and [shell reference](https://github.com/omacom/omarchy/blob/quattro/docs/omarchy-shell.md).
- Keep state-machine and formatting logic independently testable; keep QML focused on host APIs and rendering.
- When a manifest exists, validate with `omarchy plugin validate <plugin-folder>` and lint every QML entry point with `qmllint -I "$OMARCHY_PATH/shell" <files>`.
- Test load/unload, enable/disable, hot reload, shell restart, suspend/resume, update, removal, keyboard behavior, and one- and multi-monitor operation in proportion to the change.
- Measure performance as the controlled difference between the same `omarchy-shell` process with FlowPause disabled and enabled. Reject new persistent processes, background sockets, steady-state subprocess polling, per-tick writes, memory growth, or hidden repaint loops.

## Distribution and Git

- Keep the manifest ID stable once published; third-party IDs must not use the reserved `omarchy.*` namespace.
- Marketplace submission is a separate owner-approved release action. Before submission, verify the public README, root license, dependencies, installation/removal behavior, preview ownership, exact plugin ID, and the marketplace's current requirements.
- Run Git commands from this repository for product changes. Do not combine private coordination-workspace files with product commits.

## Agent skills

### Issue tracker

Issues and specifications are tracked in GitHub Issues. See `docs/agents/issue-tracker.md`.

### Triage labels

The repository uses the five default triage workflow labels. See `docs/agents/triage-labels.md`.

### Domain docs

This is a single-context repository. See `docs/agents/domain.md`.
