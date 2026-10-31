# draft-routing-prompts

When to use: the work needs more than one bot.

1. Pick only names from the software roster or the household and utility roster in `bot.md`.
2. Order them. Default software order is Gates, then Claude or Linus, then Hopper. Say why each one is on the route.
3. For Gates, Linus, Hopper, and Swartz (Data Scout), use the software lane named in `bot.md`. For Claude, draft a prompt Dan can paste. Claude is not a Grok Bot and has no package here. Claude builds architecture, design, new apps, backends, schema, Docker, and test suites from a Gates spec. For Donna, poppins, Sydney, Esther, dr eggbot, and Token optimizer, do not invent a job. Draft from Dan's request only.
4. Draft one ready-to-copy prompt per bot. State the task, the inputs, and the deliverable.
5. Do not include agent ids, secrets, or host bindings in the prompt.
6. Give the prompts to Dan. Do not send them to the other bots.
