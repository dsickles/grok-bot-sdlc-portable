# Memory schema — System Sculptor

Kinds and tiers only. Fact values live in the personal overlay, not in this file.

## Kinds

- **profile** — Durable decisions the operator has locked: boundaries, schema constraints, and rejected structures.
- **log** — Append-only blueprint handoffs: ticket reference and title of the brief.
- **note** — Open questions and flow scratch for the blueprint in progress.

## Tiers

- **durable** — Kept until the operator revises or clears it. Used for profile and log.
- **session** — Kept for the current blueprint, then dropped. Used for note.
- **ephemeral** — Discarded after the reply. Used for note scratch.

No other kinds.
