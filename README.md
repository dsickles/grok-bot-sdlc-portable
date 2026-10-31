# Grok Bot portability package

This repository is the V1 pilot package for host-agnostic Grok Bot definitions. Public markdown describes each bot's job. A human can recreate that job on another host by reading these files. Identity, account bindings, and secret values stay in a private overlay that is not part of a fresh clone.

V1 is the package format only. It does not import bots into OpenClaw, Hermes, or any other host. Package version, assumed host capabilities, and the connector catalog are normative in [PLATFORM.md](PLATFORM.md). This README does not add harness or connector requirements beyond that file.

## Public vs personal

Tracked paths are the job. They contain no live account ids, agent ids, or secret values. Gates's create rule names the assignee as D S. Janet's instructions and Data Scout's instructions name Dan as the person they assist. Filled account bindings stay in the personal overlay.

| Location | Contents | In git |
| --- | --- | --- |
| `bots/<slug>/bot.md`, `memory.schema.md`, `secrets.manifest.md`, `skills/`, `routines/` | Role, instructions, hard stops, memory kinds, secret names, skills, recipes | Yes |
| `bots/<slug>/personal.example/` | Empty stubs that show the overlay shape | Yes |
| `bots/<slug>/.personal/` | Filled memory, bindings, and secrets for one operator | No |

`personal.example/` stays tracked. `.personal/` is gitignored. Filled values belong only under `.personal/` after the copy below.

## Folder map

Five Grok Bots ship in this package. Claude is not a Grok Bot and has no folder here.

| Folder | Role | Lane |
| --- | --- | --- |
| `bots/lifecycle-lead-gates/` | Lifecycle Lead (Gates) | Ideas, Linear tickets, and specs for Claude |
| `bots/code-mechanic-linus/` | Code Mechanic (Linus) | Maintenance, AI Digest merges, ops, and smaller changes |
| `bots/pr-admiral-hopper/` | PR Admiral (Hopper) | Pull-request review only. Never merges |
| `bots/data-scout-swartz/` | Data Scout (Swartz) | AI Digest and research |
| `bots/chief-of-staff-janet/` | Chief of Staff (Janet) | General assistant, routing, and the Grok Bot bridge |

## Handoff order

1. Gates logs the idea and files the Linear ticket when asked. He writes the spec for Claude in the claude-build-spec template, with tests first.
2. Claude or Linus builds. Claude (Claude Code and Claude Pro) builds from that spec when the work is a new app, a backend, a schema or architecture change, Docker, a test suite, or design. Architecture and design happen in that build. Linus takes maintenance, AI Digest merges, ops, and smaller changes on existing codebases. Split Linus from Claude by risk, not by whether the work is new. Claude is Linus's backup only when Dan asks.
3. Hopper reviews the pull request, including Claude's pull requests. Hopper never merges.
4. Dan merges build pull requests. Hopper never merges. Linus merges AI Digest changes when that is the assignment.

Swartz runs AI Digest and research. That work does not block the path. Digest merges go to Linus. Lifecycle follow-up goes to Gates. Gates also writes public documentation when asked, and that writing does not block the path. Janet answers direct questions and drafts routing prompts. She does not message the other Grok Bots. Claude calls Janet's webhook through its grokbot-bridge skill for X data, scheduled jobs, and teammate handoffs.

## Tooling grid

The tooling grid is a default guide, not a strict rule. Dan's explicit assignment overrides it. Hopper never merging is a hard stop, not a row Dan can waive.

| Work | Default | Who |
| --- | --- | --- |
| Ideas, Linear tickets, specs (tests first) | claude-build-spec template | Gates |
| New apps, backends, schema and architecture changes, Docker, test suites, design | Claude Code and Claude Pro | Claude (not a Grok Bot) |
| Maintenance, AI Digest merges, ops, smaller changes on existing codebases | Code Mechanic | Linus |
| Pull-request review | Review only | Hopper never merges. Dan merges build pull requests |
| AI Digest and research | Data Scout | Swartz |
| X data, scheduled jobs, teammate handoffs | Janet's webhook via grokbot-bridge | Claude calls Janet |

## First run (personal overlay)

Use this once per bot slug after clone. The host may perform the same copy. The host may also prompt for names listed in `secrets.manifest.md` and write the answers into `.personal/secrets`.

1. Choose a slug from the folder map.
2. If `bots/<slug>/.personal/` does not exist, copy `bots/<slug>/personal.example/` to `bots/<slug>/.personal/`.
3. Edit only files under that `.personal/` directory:
   - `memory.md`: fill the commented headings. Those headings match the kinds and tiers in `memory.schema.md`.
   - `bindings.md`: replace each `REPLACE_ME` and fill empty keys with this operator's resource ids. Leave a key empty when it is unused.
   - `secrets`: one empty assignment line per env var name in `secrets.manifest.md`. These V1 manifests list no bot-local env vars, so the stub has no assignment lines. Values, when a name exists, belong only in `.personal/secrets`.
4. Leave `personal.example/` unchanged.
5. Do not stage `.personal/`. Git ignores `bots/*/.personal/`.

A public clone with no `.personal/` is enough to recreate the job. It is not enough to act on a specific person's accounts.

## Recreate a bot on another host

1. Read [PLATFORM.md](PLATFORM.md). Confirm the host provides the capabilities listed there, and any connector slugs named on that bot's `Depends on` line. When `bot.md` has no `Depends on` line, the job does not require a fleet connector.
2. Load `bots/<slug>/bot.md` as the bot's role, instructions, and hard stops.
3. Configure memory with the kinds and tiers in `memory.schema.md` only.
4. Register each skill named in `skills/SKILLS.md`. The skill body is the sibling markdown file in `skills/`.
5. Register each recipe in `routines/`. Use the intent, trigger type, and placeholders in that file. Bind concrete channels, inboxes, repositories, and allowlists only from `.personal/bindings.md` after the first-run copy.
6. Complete [First run (personal overlay)](#first-run-personal-overlay) before the bot touches live resources.

No further setup document is part of this package.
