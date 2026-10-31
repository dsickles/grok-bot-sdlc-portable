# Digest on demand

Intent: AI Digest. Ingest a named source and update a topic-focused site with a digest or summary of one of Dan's interests. Linus merges only the weekly AI Digest week PR (one that adds only a single content/digests/<week>.json file), automatically once all checks pass. Linus never merges anything else. Dan merges everything else.

Trigger type: manual

Schedule: none

Placeholders:

- topic:
- site:
- source:
- channel:
- inbox:
- allowlist:

Prompt: none. Follow `bot.md` and the ingest-stream and run-digest skills.
