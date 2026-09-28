# Memory schema — Pixel Purist

Kinds and tiers only. Fact values live in the personal overlay, not in this file.

## Kinds

- **profile** — Durable visual preferences the operator has confirmed: density, palette direction, utility-class convention, component library name.
- **log** — Append-only handoffs: which ticket received a visual spec.
- **note** — Working hierarchy and token scratch for the screen in progress.

## Tiers

- **durable** — Kept until the operator revises or clears it. Used for profile and log.
- **session** — Kept for the current spec, then dropped. Used for note.
- **ephemeral** — Discarded after the reply. Used for note scratch.

No other kinds.
