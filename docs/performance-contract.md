# Performance and Shell-Safety Contract

**Status:** Provisional acceptance contract for the bounded feasibility spike

FlowPause runs inside the shared `omarchy-shell` process. Its resource cost must
therefore be measured as the controlled difference between the same pinned
Omarchy environment with FlowPause disabled and enabled. A standalone FlowPause
PID is not expected.

## Design invariants

The spike fails review if it introduces:

- an additional persistent process;
- network connections or background network requests;
- periodic subprocess launches during steady-state operation;
- state writes for countdown ticks;
- more than one canonical scheduler across monitors;
- a repaint or animation loop while prompt UI is hidden;
- unbounded history, queues, logs, caches, or state files; or
- expensive prompt objects that remain alive while the prompt is closed.

FlowPause must fail open: it must not trap input, duplicate prompts across
monitors, or destabilize the shell when state is missing, malformed, stale, or
unwritable.

## Controlled measurement

Record the exact Omarchy revision, FlowPause revision, hardware, display layout,
measurement tools, sample duration, and relevant environment configuration.
Compare disabled and enabled runs under the same conditions for:

1. stabilized idle operation;
2. normal keyboard and window activity;
3. a visible bar countdown;
4. prompt open, interaction, and close;
5. repeated prompt open/close cycles;
6. extended idle and active-use soaks;
7. shell restart and plugin disable/re-enable;
8. suspend/resume, lock/unlock, clock discontinuity, and stale deadlines;
9. theme changes and display hot-plug; and
10. one- and two-monitor layouts.

Measure CPU, RSS/PSS, thread and child-process activity, timer wakeups, state-file
writes, unexpected sockets, prompt latency, memory slope, shell errors, and
duplicate or missed prompts. Retain raw samples rather than only summarized
results.

## Provisional budgets

These are validation thresholds, not claims that the current code meets them.

| Metric | Acceptance budget |
| --- | --- |
| Persistent processes | No process beyond the already-running `omarchy-shell` |
| Idle CPU | Enabled-minus-disabled median below 0.1 percentage point of one core; p95 below 0.5 under a fixed idle workload |
| Incremental steady memory | At most 5 MiB RSS/PSS after warm-up and no monotonic growth over 1 MiB during an eight-hour soak |
| Hidden-state wakeups | No repaint loop and no more than one scheduled QML wake per minute outside an imminent prompt; prefer waking at the next deadline |
| Visible countdown | No faster than once per second; once per minute when displaying minute precision |
| State writes | Meaningful transitions only; never once per second; state remains small and bounded |
| Prompt latency | Warm p95 at or below 100 ms and cold p95 at or below 250 ms from due event to visible surface |
| Reliability | No duplicate, missed, or immediately stale prompt after restart or resume; no shell crash or QML error |
| Privacy and network | No network socket and no activity-content persistence |

If measurement noise exceeds a budget, extend the sample and report uncertainty
instead of claiming a pass. Relaxing a budget requires measured evidence, an
explicit trade-off, and an accepted architectural decision.

## Platform references

- [Omarchy plugin development guide](https://plugins.omarchy.org/develop.html)
- [Omarchy shell reference](https://github.com/omacom/omarchy/blob/quattro/docs/omarchy-shell.md)
- [Omarchy plugin security policy](https://github.com/omacom/omarchy-plugin-marketplace/blob/main/SECURITY.md)
