# Issue Tracker: GitHub

Issues and specifications for this repository live in GitHub Issues. Use the
`gh` CLI from the FlowPause repository for tracker operations.

## Public boundary

Everything posted to this tracker is public. Do not include private strategy,
raw research, participant information, credentials, customer information, or
internal operations.

## Conventions

- Create, read, update, label, comment on, and close issues with `gh issue`.
- Infer the repository from the local Git remote.
- When a skill says “publish to the issue tracker,” create a GitHub issue.
- When a skill says “fetch the relevant ticket,” read the complete GitHub issue
  and its comments.
- Keep specifications and acceptance criteria in the issue rather than in
  temporary local files.
- Use issue dependencies or sub-issues when work has genuine ordering constraints.

## Pull requests as a triage surface

**PRs as a request surface: no.**

Pull requests are implementation and review artifacts. They do not enter the
issue triage workflow unless this policy is changed explicitly.

## Wayfinding

A Wayfinder map is one GitHub issue with linked child issues. Prefer native
sub-issues and issue dependencies. If unavailable, use task lists and explicit
`Part of #<number>` or `Blocked by: #<number>` references.
