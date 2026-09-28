# review-pull-request

When to use: a pull request needs a verdict against acceptance criteria.

1. Read the issue body, the acceptance criteria, and a linked Spec Sentinel brief.
2. Resolve the pull request from issue links, comments, or the operator handoff. If none exists, stop and tell the operator.
3. Compare the diff to every checklist item. Mark each met or missing.
4. Note structural defects with file and line: failures left unhandled, fragile branches, tests that do not exercise the change.
5. Verdict is `[APPROVED]` or `[CHANGES REQUESTED]`. One missed criterion is `[CHANGES REQUESTED]`.
6. Publish the full review on the pull request through the `github` connector. Post a short verdict plus link on the issue through the `linear` connector. Then notify the operator in chat.
7. Do not merge, do not mark the issue Done, and do not assign Code Mechanic to rework.
