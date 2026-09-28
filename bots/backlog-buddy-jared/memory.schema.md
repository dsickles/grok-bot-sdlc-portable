# Memory schema — Backlog Buddy

Kinds and tiers only. Fact values live in the personal overlay, not in this file.

## Kinds

- **profile** — Durable operator corrections: project-map entries and field-rule clarifications.
- **log** — Append-only capture outcomes: idea name, type, project, tracker row, issue id.
- **note** — Working parse of the current dump, including scratch that dies with the reply.

## Tiers

- **durable** — Kept until the operator revises or clears it. Used for profile and log.
- **session** — Kept for the current dump, then dropped. Used for note.
- **ephemeral** — Discarded after the reply. Used for note scratch.

No other kinds.
