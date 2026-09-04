# FlowPause Product Contract

**Status:** Current public implementation boundary

This document contains the product decisions, hypotheses, and unknowns that
public implementation work may rely on. It deliberately excludes private
research, participant information, strategy, and operations.

## Interpretation

- **Decision:** an accepted constraint on product or implementation work.
- **Hypothesis:** a belief that still requires behavioral or concept evidence.
- **Unknown:** a question that must remain visible until research or a technical
  experiment resolves it.

## Product boundary

**Decision:** FlowPause is a respectful, resource-efficient break companion for
Omarchy 4 / Quattro. It serves individually motivated users and is not a medical
application, workforce-monitoring product, strict website blocker, or official
Omarchy product.

**Hypothesis:** The initial user is an Omarchy user who already values breaks but
finds existing reminders too poorly timed, controlling, confusing, or expensive
to keep enabled.

**Unknown:** It has not yet been established that this is a frequent,
consequential, and underserved problem among Omarchy users.

## Product principles

The following are decisions:

1. Respect attention: every interruption must justify itself.
2. Protect autonomy: blocking behavior is never the default.
3. Start gently: strong defaults should not impose an aggressive schedule.
4. Keep actions obvious: take now, snooze, skip, pause, and resume must require
   little thought.
5. Prefer clarity over extensive configuration.
6. Keep user state local and collect no unrelated activity content.
7. Use documented Omarchy contracts, semantic theme tokens, and keyboard-first
   interaction patterns.
8. Add no persistent process, network activity, polling loop, hidden animation,
   or per-tick disk write without measured evidence and a new decision.
9. Use calm language without guilt, punishment, or streak pressure.
10. Make no medical, injury-prevention, focus-improvement, or productivity
    claims without product-specific evidence.

## Interruption behavior

The following are decisions for the intended product:

- Give advance notice before a due break.
- Never block the screen by default.
- Keep take now, snooze, skip, and pause immediately available.
- Provide a manual way to pause reminders for a meeting or focused session.
- Reconcile elapsed and away time before presenting a prompt after restart,
  unlock, or system resume.
- Treat away time as possible rest instead of blindly continuing the schedule.
- Preserve keyboard access, accessible semantics, contrast, and reduced-motion
  behavior in every user-facing surface.

**Hypothesis:** Privacy-preserving awareness of idle, fullscreen, presentation,
or meeting context could improve prompt timing.

**Unknown:** Which context signals are stable, private, inexpensive, and useful
enough to include. Manual pause is the fallback until this is demonstrated.

## Current authorized scope

**Decision:** The next implementation is a bounded host-contract and resource
spike, not the complete product. It may establish only enough behavior to test:

- manifest validation and plugin lifecycle;
- one shared scheduling owner and consistent multi-monitor state;
- a minimal bar widget and an on-demand empty prompt surface;
- absolute-deadline reconciliation across restart and suspend/resume;
- bounded local persistence and fail-open behavior; and
- controlled enabled-versus-disabled resource measurement.

Broader feature work, automatic context detection, concept-polished UI,
marketplace submission, marketing, accounts, telemetry, cloud synchronization,
non-Omarchy support, and medical or productivity claims remain outside this
scope.

## Decision gate after the spike

The spike does not establish product feasibility merely by loading successfully.
Proceeding requires evidence that the pure plugin can meet the architecture,
lifecycle, privacy, and performance contracts without destabilizing the shared
shell. Product expansion additionally requires a differentiated user problem;
technical feasibility is not evidence of demand.
