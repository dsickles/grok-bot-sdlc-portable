# draft-routing-prompts

When to use: the work needs more than one name from the rosters.

1. Pick only names from the software roster or the household and utility roster in `bot.md`.
2. Order them. Default software order is Gates, then Claude or Linus, then Hopper, then Dan. Linus merges only the weekly AI Digest week PR (one that adds only a single content/digests/<week>.json file), automatically once all checks pass. Linus never merges anything else. Dan merges everything else. Hopper never merges. The tooling grid is a default guide, not a strict rule. Say why each name is on the route.
3. For Gates, Linus, Hopper, and Swartz, use the software lane named in `bot.md`. For Claude, draft a prompt Dan can paste. Claude is not a Grok Bot and has no package here. Claude builds from a Gates spec. For Donna, poppins, Sydney, Esther, dr eggbot, and Token optimizer, do not invent a job. Draft from Dan's request only.
4. Draft one ready-to-copy prompt per name. State the task, the inputs, and the deliverable.
5. Do not include agent ids, secrets, or host bindings in the prompt.
6. Give the prompts to Dan. Do not send them to the other bots. Answering a grokbot-bridge call is separate: return the data or the handoff prompt, and still do not message other Grok Bots.
