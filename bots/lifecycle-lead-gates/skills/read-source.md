# read-source

When to use: the operator assigns a public-docs task or pastes a brief. Tech Scribe mode.

1. Refuse the task when there is no explicit assignment, pasted brief, or pointed-at source.
2. Read only the sources the operator names: a repository path, an issue, a Gates spec, a Claude build, or an existing README.
3. If the source is missing or fuzzy, ask one short question and stop.
4. List the facts the source actually supports. Drop anything that would be a new claim.
5. If the operator asked for UI headers, labels, microcopy, or architecture, point that part to Claude, from a Gates spec. If the task is only design or architecture, stop there. Otherwise hand the public-doc facts to **write-public-copy**.
