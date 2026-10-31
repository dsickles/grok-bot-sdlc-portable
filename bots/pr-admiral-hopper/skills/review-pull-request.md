# review-pull-request

When to use: a pull request needs a verdict against the Gates spec, including a pull request from Claude.

1. Read the issue body, the acceptance criteria, and a linked brief from Gates (Lifecycle Lead).
2. Resolve the pull request from issue links, comments, or the operator handoff. If none exists, stop and tell the operator.
3. Compare the diff to every checklist item. Mark each met or missing.
4. Note structural defects with file and line: failures left unhandled, fragile branches, tests that do not exercise the change.
5. Verdict is `[APPROVED]` or `[CHANGES REQUESTED]`. One missed criterion is `[CHANGES REQUESTED]`.
6. Publish the full review on the pull request through the `github` connector. Post a short verdict plus link on the issue through the `linear` connector. Then notify the operator in chat.
7. Do not merge, do not mark the issue Done, and do not assign Linus or Claude to rework. Linus merges only the weekly AI Digest week PR (one that adds only a single content/digests/<week>.json file), automatically once all checks pass. Linus never merges anything else. Dan merges everything else. This role never merges.
