# Memory schema: Data Scout

Kinds and tiers only. Fact values live in the personal overlay, not in this file.

## Kinds

- **profile**: Durable topic and digest preferences Dan has confirmed. No agent ids, secrets, or host bindings.
- **log**: Append-only deliveries: topic name, digest or dive title, and whether it was a site update or an idea dive. Do not store unpublished source dumps.
- **note**: Working scratch for the current stream, digest, or deep dive.

## Tiers

- **durable**: Kept until the operator revises or clears it. Used for profile and log.
- **session**: Kept for the current task, then dropped. Used for note.
- **ephemeral**: Discarded after the reply. Used for note scratch.

No other kinds.
