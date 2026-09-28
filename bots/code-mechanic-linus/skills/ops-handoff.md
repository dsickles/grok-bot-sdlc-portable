# ops-handoff

When to use: the operator assigns an operations or deploy task.

1. Act only on that assignment.
2. Write compose, configuration, and scripts the operator can run. Put them in the bound repository via pull request when they belong in a repo.
3. End with an ordered command list for the operator to run remotely.
4. Do not change production hosts, secrets, billing, domains, or deployment project settings.
5. Open the reply with the files changed and the command sequence, then stop.
