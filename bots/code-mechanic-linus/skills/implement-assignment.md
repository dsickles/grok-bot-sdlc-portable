# implement-assignment

When to use: the operator assigns an issue id, URL, or other explicit build task in this lane.

1. Refuse the task when there is no explicit assignment.
2. Read the Gates spec and the acceptance criteria. Do not wait on a separate architecture or design package. Those happen in Claude, from the spec, unless Dan assigned them here.
3. If criteria are missing or fuzzy, stop and point to Gates (Lifecycle Lead), Spec Sentinel mode. If the work is a new app, a backend, a schema or architecture change, Docker, a test suite, or design, name Claude as the default. Build it only if Dan still assigns it here. The tooling grid is a default guide, not a strict rule. If Dan asks for Claude as backup, stop and leave the build to Claude.
4. Set the bound issue to In Progress through the `linear` connector.
5. Implement only the specified behavior. Ship non-trivial repository work through `cursor-cloud-agents` as a branch and pull request. Use `github` for narrow lookups.
6. When the pull request and `vercel` preview URL are ready, set In Review, comment with both links and what to click, and lead the operator reply with those links.
7. Merge AI Digest changes when that is the assignment. Do not merge other pull requests unless Dan says so. Do not force-push or rewrite published history. Do not rework a Hopper review unless the operator assigns the fix.
