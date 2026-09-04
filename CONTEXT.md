# FlowPause

FlowPause helps an individual Omarchy user maintain a chosen work-and-break
rhythm without surrendering control of their desktop or attention.

## Product and rhythm

**Break companion**:
A tool that supports a chosen break rhythm while leaving the user in control.
_Avoid_: Health application, enforcement tool, productivity monitor

**Schedule**:
The user's current work-and-break rhythm, including the next expected change.
_Avoid_: Timer configuration, routine

**Work interval**:
The scheduled period between breaks.
_Avoid_: Focus session, Pomodoro

**Upcoming warning**:
Advance notice that a break will soon become due.
_Avoid_: Pre-break alarm, interruption

**Due break**:
A break the schedule currently recommends taking.
_Avoid_: Mandatory break, overdue violation

**Break**:
A period the user chooses to spend away from the current work interval.
_Avoid_: Lockout, penalty, compliance period

**Away time**:
A period when the user is not actively using the computer and which may satisfy
some or all of a due break after reconciliation.
_Avoid_: Inactivity failure, missed work

## User actions

**Take now**:
Start a break immediately, whether or not one is already due.
_Avoid_: Force break

**Snooze**:
Defer the current due break for a bounded interval while keeping it pending.
_Avoid_: Pause, skip, dismiss

**Skip**:
Decline the current due break and continue the schedule.
_Avoid_: Snooze, pause

**Pause**:
Temporarily suspend future break prompts until the schedule is resumed.
_Avoid_: Snooze, disable

**Resume schedule**:
End a pause and return to the chosen schedule.
_Avoid_: System resume, plugin enable

## Experience

**Break prompt**:
The nonblocking surface that presents a due break and its immediate actions.
_Avoid_: Lock screen, enforcement screen, alarm

**Reconciliation**:
The interpretation of elapsed time and away time after a lifecycle gap so the
schedule does not produce a stale or duplicate break prompt.
_Avoid_: Blind timer continuation, catch-up notification
