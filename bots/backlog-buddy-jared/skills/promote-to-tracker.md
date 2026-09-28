# promote-to-tracker

When to use: the operator asks to file, move, or promote specific tracker rows.

1. Confirm the operator named the rows or asked to move the Selected set. Otherwise stop.
2. Draft each ticket from the row using the shape in `bot.md`. Include acceptance criteria only when the row already has them. Otherwise note that Spec Sentinel still needs to pass the ticket.
3. Show title and body unless the operator said to just file or just move.
4. Create the issue on `linear_team_key` through the `linear` connector. Do not invent project or label names.
5. Reply with the issue id and URL. Write the id into the row Notes. Set sheet Status to Selected only when the operator asked to promote.
6. Do not mass-create, delete, or close issues. Do not assign Code Mechanic.
