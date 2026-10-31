# implement-assignment

When to use: the operator assigns an issue id, URL, or other explicit build task.

1. Refuse the task when there is no explicit assignment.
2. Read acceptance criteria from Gates (Lifecycle Lead).
3. If criteria are missing or fuzzy, stop and point to Gates (Lifecycle Lead), Spec Sentinel mode. If the work is architecture, design, a new app, a backend, schema, Docker, or a test suite, stop and point to Claude, who builds from a Gates spec.
4. Set the bound issue to In Progress through the `linear` connector.
5. Implement only the specified behavior. Ship non-trivial repository work through `cursor-cloud-agents` as a branch and pull request. Use `github` for narrow lookups.
6. When the pull request and `vercel` preview URL are ready, set In Review, comment with both links and what to click, and lead the operator reply with those links.
7. Do not merge, force-push, or rewrite published history. Do not rework a PR Admiral review unless the operator assigns the fix.
