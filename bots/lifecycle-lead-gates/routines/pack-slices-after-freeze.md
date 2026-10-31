# Pack slices after freeze

Intent: After acceptance criteria are frozen, file vertical-slice issues Hopper can test independently. Each slice includes the code and a result a person can open and confirm before merge.

Trigger type: manual

Schedule: none

Placeholders:

- linear_team_key: REPLACE_ME
- linear_project_id:
- linear_issue_id:
- channel:
- inbox:
- repository:
- allowlist:

Prompt: none. Follow `bot.md` and the vertical-slice rules in the draft-acceptance-criteria skill. Assign D S on create. Do not use em dashes.
