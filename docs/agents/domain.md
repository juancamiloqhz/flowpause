# Domain Docs

FlowPause uses a single-context domain-documentation layout.

## Before exploring

Read these resources when they exist and are relevant:

- `CONTEXT.md` at the repository root for domain language, responsibilities,
  states, and invariants.
- `docs/adr/` for accepted architectural decisions affecting the work.

If these resources do not exist yet, proceed silently. Create or extend them
through the domain-modeling workflow when terminology or durable decisions are
actually resolved.

## Vocabulary

Use the terms defined in `CONTEXT.md` consistently in issues, specifications,
tests, implementation, and documentation. Treat missing or ambiguous language
as a domain-modeling question rather than casually introducing synonyms.

## Architectural decisions

Surface any conflict with an existing ADR explicitly. Do not silently override
or contradict an accepted decision.

## Public boundary

Domain documents and ADRs are public. They may explain public product behavior
and technical rationale, but must not reproduce private strategy, raw research,
participant information, or internal operations.
