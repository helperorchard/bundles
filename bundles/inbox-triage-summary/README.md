# Inbox Triage Summary

Which emails need you today, and which can wait. Weekdays at 8:00, before the day gets loud.

Who matters most is written in `memory.md`. Weekday 8:00 sits in `routines.yaml`. The sorting method is `skills/inbox-triage-summary/SKILL.md`, the Goose copy is `goose-recipe.yaml`, and `mcp.json` is left for a mailbox you already use.

## Install

skills.sh CLI (Claude Code, Cursor, Codex, Goose, OpenClaw and more)
```
npx skills add helperorchard/bundles --skill inbox-triage-summary
```

Hermes Agent
```
hermes skills install helperorchard/bundles/bundles/inbox-triage-summary/skills/inbox-triage-summary
hermes cron create "0 8 * * 1-5" "Run inbox-triage-summary on my new email and give me the reply-today list first." --skill inbox-triage-summary
```
Add the lines from `memory.md` to `~/.hermes/memories/MEMORY.md`.

Goose recipe and schedule
```
goose run --recipe goose-recipe.yaml
goose schedule add --schedule-id inbox-triage-summary --cron "0 0 8 * * 1-5" --recipe-source ./goose-recipe.yaml
```

Manual copy: put `skills/inbox-triage-summary` in `~/.agents/skills/` (Codex, Goose, Cursor) or `~/.claude/skills/` (Claude Code).

## Connectors
Mail can be pasted, or read through a mailbox you already connected.

License: MIT. Original writing by Drok AI.
