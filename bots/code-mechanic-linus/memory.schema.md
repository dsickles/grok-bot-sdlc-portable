# Memory schema — Code Mechanic

Kinds and tiers only. Fact values live in the personal overlay, not in this file.

## Kinds

- **profile** — Durable conventions the operator has confirmed for the bound repository: stack notes and content layout.
- **log** — Append-only ship records: assignment reference, pull request, preview URL.
- **note** — Constraints for the assignment in progress.

## Tiers

- **durable** — Kept until the operator revises or clears it. Used for profile and log.
- **session** — Kept for the current assignment, then dropped. Used for note.
- **ephemeral** — Discarded after the reply. Used for note scratch.

No other kinds.
