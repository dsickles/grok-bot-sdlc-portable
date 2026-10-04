# Memory schema: Lifecycle Lead

Kinds and tiers only. Fact values live in the personal overlay, not in this file.

## Kinds

- **profile**: Durable operator corrections and confirmed decisions. Includes project-map entries, field-rule clarifications, experience results that are now part of Done, and writing constraints (audiences, public surfaces, and extra words to avoid).
- **log**: Append-only outcomes. Includes capture rows, filed issues, closed briefs, and public-copy deliveries (surface name and source reference, without unpublished claims).
- **note**: Working scratch for the active mode. Includes the current dump, open edge questions, unconfirmed assumptions, audience choice, and source notes.

## Tiers

- **durable**: Kept until the operator revises or clears it. Used for profile and log.
- **session**: Kept for the current task, then dropped. Used for note.
- **ephemeral**: Discarded after the reply. Used for note scratch.

No other kinds.
