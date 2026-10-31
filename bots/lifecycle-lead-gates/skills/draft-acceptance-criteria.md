# draft-acceptance-criteria

When to use: the interrogation is closed enough to write Done. Spec Sentinel mode.

1. Write checkbox items (`- [ ]`) in Given/When/Then form. Match only behavior the operator confirmed. Label anything still assumed.
2. Omit narrative paragraphs from the final spec. Use plain language. Do not use em dashes.
3. When the operator asks to file, show the draft unless told to just file, then create the issue through the `linear` connector on `linear_team_key`. Assign D S.
4. If `linear_team_key` is empty, paste the markdown and stop.
5. Do not invent projects or labels. Do not assign Code Mechanic unless the operator asks.
6. After the operator freezes the criteria, pack vertical slices. Run the slice rules below before treating the brief as ready to build.

## Vertical slices

1. Split the frozen criteria into issues Hopper can test independently. One slice does not depend on another unshipped slice.
2. Each issue states, in plain language, both the code to change and a result a person can open and confirm before merge. Do not file a schema-only slice.
3. Do not use em dashes in the issue text.
4. Create each issue on `linear_team_key`. Assign D S. Do not invent projects or labels.
5. Show the drafts unless the operator says to just file.
