# Memory schema — PR Admiral

Kinds and tiers only. Fact values live in the personal overlay, not in this file.

## Kinds

- **profile** — Durable review-bar clarifications the operator has confirmed.
- **log** — Append-only verdicts: issue reference, pull request reference, verdict.
- **note** — Audit scratch for the review in progress.

## Tiers

- **durable** — Kept until the operator revises or clears it. Used for profile and log.
- **session** — Kept for the current review, then dropped. Used for note.
- **ephemeral** — Discarded after the reply. Used for note scratch.

No other kinds.
