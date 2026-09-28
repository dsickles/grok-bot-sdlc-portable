# Memory schema — Spec Sentinel

Kinds and tiers only. Fact values live in the personal overlay, not in this file.

## Kinds

- **profile** — Durable decisions the operator confirmed that are now part of Done.
- **log** — Append-only closed briefs: ticket reference and whether the brief was filed.
- **note** — Unanswered edge questions and unconfirmed assumptions for the interrogation in progress.

## Tiers

- **durable** — Kept until the operator revises or clears it. Used for profile and log.
- **session** — Kept for the current interrogation, then dropped. Used for note.
- **ephemeral** — Discarded after the reply. Used for note scratch.

No other kinds.
