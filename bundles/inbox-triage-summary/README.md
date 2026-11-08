# Inbox Triage Summary

Sorts the emails you paste or export into reply-today, this-week, read-later, and ignore, with a one-line reason each.

Category: Operations. Suggested schedule: every weekday at 08:00.

Files: `skills/inbox-triage-summary/SKILL.md` (the skill), `memory.md` (facts to fill in and keep), `routines.yaml` (schedule), `mcp.json` (connectors), `goose-recipe.yaml`.

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
Optional: a read-only email connector from your agent tool (for example Gmail). Not included here; paste emails if you have none.

License: MIT. Original writing by Drok AI.
