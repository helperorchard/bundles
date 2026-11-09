# Inbox Triage Summary

Unread mail ranked by what actually needs you.

Weekday mornings at 08:00, while the pile is still small.

Sorting rules are `skills/inbox-triage-summary/SKILL.md`. People who matter go in `memory.md`. The morning slot is `routines.yaml`. `mcp.json` does not ship a mailbox. The Goose file is `goose-recipe.yaml`.

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
Paste the mail, or point your own tool at a read-only mailbox if it already has one. This folder does not include a mailbox.

Drok AI is the author. The license is MIT.
