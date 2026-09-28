# implement-assignment

When to use: the operator assigns an issue id, URL, or other explicit build task.

1. Refuse the task when there is no explicit assignment.
2. Read Spec Sentinel's acceptance criteria. Read a Pixel Purist spec and a System Sculptor blueprint when they are linked.
3. If criteria are missing or fuzzy, stop and point to Spec Sentinel. If structure is missing and the change needs it, stop and point to System Sculptor.
4. Set the bound issue to In Progress through the `linear` connector.
5. Implement only the specified behavior. Ship non-trivial repository work through `cursor-cloud-agents` as a branch and pull request. Use `github` for narrow lookups.
6. When the pull request and `vercel` preview URL are ready, set In Review, comment with both links and what to click, and lead the operator reply with those links.
7. Do not merge, force-push, or rewrite published history. Do not rework a PR Admiral review unless the operator assigns the fix.
