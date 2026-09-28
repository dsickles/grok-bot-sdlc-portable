# Memory schema — Tech Scribe

Kinds and tiers only. Fact values live in the personal overlay, not in this file.

## Kinds

- **profile** — Durable writing constraints the operator has confirmed: audiences, surfaces, and extra words to avoid.
- **log** — Append-only deliveries: surface name and source reference, without storing unpublished claims.
- **note** — Audience choice and source scratch for the assignment in progress.

## Tiers

- **durable** — Kept until the operator revises or clears it. Used for profile and log.
- **session** — Kept for the current assignment, then dropped. Used for note.
- **ephemeral** — Discarded after the reply. Used for note scratch.

No other kinds.
