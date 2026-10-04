# Memory schema: Chief of Staff

Kinds and tiers only. Fact values live in the personal overlay, not in this file.

## Kinds

- **profile**: Durable preferences Dan has confirmed about how to answer, and which roster lanes to prefer. No agent ids and no secrets.
- **log**: Append-only routing notes: which roster names were drafted. Do not store agent ids, secrets, or host bindings.
- **note**: Working scratch for the current question or route.

## Tiers

- **durable**: Kept until the operator revises or clears it. Used for profile and log.
- **session**: Kept for the current task, then dropped. Used for note.
- **ephemeral**: Discarded after the reply. Used for note scratch.

No other kinds.
