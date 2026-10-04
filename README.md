# Grok Bot portability package

This repository is the V1 pilot package for host-agnostic Grok Bot definitions. Public markdown describes each bot's job. A human can recreate that job on another host by reading these files. Identity, account bindings, and secret values stay in a private overlay that is not part of a fresh clone.

V1 is the package format only. It does not import bots into OpenClaw, Hermes, or any other host. Package version, assumed host capabilities, and the connector catalog are normative in [PLATFORM.md](PLATFORM.md). This README does not add harness or connector requirements beyond that file.

## Public vs personal

Tracked paths are the job. They contain no live account ids, agent ids, or secret values. Gates's create rule names the assignee as D S. Janet's instructions name Dan as the person she assists. Filled account bindings stay in the personal overlay.

| Location | Contents | In git |
| --- | --- | --- |
| `bots/<slug>/bot.md`, `memory.schema.md`, `secrets.manifest.md`, `skills/`, `routines/` | Role, instructions, hard stops, memory kinds, secret names, skills, recipes | Yes |
| `bots/<slug>/personal.example/` | Empty stubs that show the overlay shape | Yes |
| `bots/<slug>/.personal/` | Filled memory, bindings, and secrets for one operator | No |

`personal.example/` stays tracked. `.personal/` is gitignored. Filled values belong only under `.personal/` after the copy below.

## Folder map

| Folder | Role | Lane |
| --- | --- | --- |
| `bots/lifecycle-lead-gates/` | Lifecycle Lead (Gates) | Backlog, acceptance criteria, and public docs |
| `bots/pixel-purist-ive/` | Pixel Purist (Ive) | UI / UX, including microcopy |
| `bots/system-sculptor-carmack/` | System Sculptor (Carmack) | Backend and architecture |
| `bots/code-mechanic-linus/` | Code Mechanic (Linus) | Implementation and DevOps |
| `bots/pr-admiral-hopper/` | PR Admiral (Hopper) | Code review and QA |
| `bots/chief-of-staff-janet/` | Chief of Staff (Janet) | General assistant and routing |

Pilot pipeline, in role names: Lifecycle Lead (Gates) grooms the backlog, locks acceptance criteria, and after that freeze packs vertical-slice issues. Code Mechanic implements on assignment. PR Admiral reviews the pull request against those criteria. System Sculptor joins when the work needs an architecture blueprint. Pixel Purist joins when the work needs a visual spec or microcopy. Lifecycle Lead also writes public documentation when the operator asks, and that writing does not block the path. Chief of Staff (Janet) answers direct questions and drafts routing prompts. She does not message the other bots. The default path can skip System Sculptor and Pixel Purist.

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
