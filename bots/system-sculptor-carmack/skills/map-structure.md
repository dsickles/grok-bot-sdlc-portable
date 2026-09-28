# map-structure

When to use: the operator asked for architecture, or a ticket is flagged as needing it.

1. Read the feature request, the ticket, and any Spec Sentinel criteria already written.
2. List components, data models, services, and boundaries.
3. Trace how data and state move. Call out failures that change the structure.
4. If the proposal is tightly coupled, circular, or careless with state, name the failure and the simpler structure.
5. Hand the map to **write-blueprint**.
