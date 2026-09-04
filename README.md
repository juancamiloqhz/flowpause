# FlowPause

FlowPause is a respectful, lightweight break companion for [Omarchy](https://omarchy.org/).

## Status

FlowPause is in early differentiation and technical-feasibility work. It is not installable yet and has no public release. The first spike will test Omarchy Quattro's plugin lifecycle, one shared scheduling service, a minimal bar widget, and incremental resource cost before the project expands into a complete product.

## Intended architecture

The preferred first implementation is a self-contained Omarchy Quattro plugin:

- one singleton `service` owns scheduling and bounded local state;
- one minimal `bar-widget` presents status and immediate controls; and
- panels or overlays load only when validated interaction requirements need them.

The initial design excludes a separate daemon, a second Quickshell process, network activity, accounts, telemetry, runtime downloads, steady-state subprocess polling, and per-tick disk writes.

## Product principles

- Respect attention and protect user autonomy.
- Never block the screen by default.
- Keep take, snooze, skip, and pause actions immediately available.
- Store only minimal local state and no unrelated activity content.
- Prefer event-driven behavior and measurable, negligible idle overhead.
- Make no medical or productivity-outcome claims.

## Development

Development instructions will be added with the first runnable spike. The plugin will target the current Omarchy 4 / Quattro contract and use the permanent plugin ID `io.github.juancamiloqhz.flowpause`.

The repository is self-contained for product implementation:

- [Domain language](CONTEXT.md)
- [Public product contract](docs/product-contract.md)
- [Architecture decisions](docs/adr/)
- [Performance and shell-safety contract](docs/performance-contract.md)
- [Engineering workflow conventions](docs/agents/)

Relevant platform references:

- [Omarchy plugin development guide](https://plugins.omarchy.org/develop.html)
- [Omarchy shell reference](https://github.com/omacom/omarchy/blob/quattro/docs/omarchy-shell.md)
- [Marketplace submission requirements](https://github.com/omacom/omarchy-plugin-marketplace/blob/main/SUBMISSION.md)

## License

[MIT](LICENSE)
