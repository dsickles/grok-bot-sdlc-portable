# Platform contract

This file is the normative contract for the V1 pilot package. `README.md` explains how a human uses the repository. It does not add host, harness, or connector requirements beyond this contract.

## Package version

`package_version: 1.0.0-v1-pilot`

## Importer compatibility

A compatible importer:

- reads this repository as a markdown package at `package_version` `1.0.0-v1-pilot`
- if `bots/<slug>/.personal/` is absent, creates it by copying `personal.example/` to `.personal/`
- when `secrets.manifest.md` lists env var names, may prompt for them and write the values into `.personal/secrets`
- does not expect a JSON schema (this version does not ship one)

A reader built for a different major version is not a compatible importer of `1.0.0-v1-pilot`.

This package does not include a live import adapter for OpenClaw, Hermes, or any other host.

## Assumed host capabilities

A host that runs one of these bots is assumed to be able to:

- load `bot.md` as the bot's instructions
- store memory entries tagged with the kinds and tiers in that bot's `memory.schema.md`
- keep an untracked `.personal/` directory per bot, created by the copy rule in this file
- read `secrets.manifest.md` and, when it lists env var names, prompt for them and store the values in `.personal/secrets`
- follow `skills/SKILLS.md` to the skill body files in the same directory
- fire a recipe in `routines/` by the trigger type written in that file

Trigger type is a label on the recipe, not a vendor scheduler:

- `manual` — the operator sends a message that asks for this recipe
- `on-assign` — the operator assigns this bot a piece of work
- `issue-status` — an issue transitions into the placeholder status named in the recipe

The host calls a fleet connector by slug when `bot.md` contains a `Depends on` line that names that slug.

## Fleet connector catalog

Slugs and types only. This catalog has no account ids. Spreadsheet ids, repository names, mailboxes, calendars, channels, and allowlists belong in `.personal/bindings.md` after the copy rule, not here.

| Slug | Type |
| --- | --- |
| `linear` | issue tracker connector |
| `github` | source hosting connector |
| `google-sheets` | spreadsheet connector |
| `google-calendar` | calendar connector |
| `gmail` | mail connector |
| `vercel` | deployment preview connector |
| `cursor-cloud-agents` | cloud coding agent connector |
| `browser-desktop` | host capability: interactive desktop browser |

Pilot `Depends on` lines use a subset of these slugs. Catalog entries with no V1 `Depends on` reference stay in the fleet catalog for later bots. A host does not need a connector that the bot's `Depends on` line omits. `browser-desktop` is a host capability, not a credentialed account. No V1 pilot bot requires it.

## Personal overlay rule

If `.personal/` is absent, copy `personal.example/` → `.personal/`. Never commit `.personal/`.

For a bot slug, that copy is `bots/<slug>/personal.example/` → `bots/<slug>/.personal/`. Keep `personal.example/` tracked and unchanged as the stub.

Secret values, filled bindings, and personal memory are valid only under `.personal/`.
