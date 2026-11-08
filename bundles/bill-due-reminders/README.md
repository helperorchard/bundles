# Bill Due Reminders

Lists the bills due in the next 10 days from your saved bill list, with amounts and which are on autopay.

Category: Personal. Suggested schedule: every Monday and Thursday at 09:00.

Files: `skills/bill-due-reminders/SKILL.md` (the skill), `memory.md` (facts to fill in and keep), `routines.yaml` (schedule), `mcp.json` (connectors), `goose-recipe.yaml`.

## Install

skills.sh CLI (Claude Code, Cursor, Codex, Goose, OpenClaw and more)
```
npx skills add helperorchard/bundles --skill bill-due-reminders
```

Hermes Agent
```
hermes skills install helperorchard/bundles/bundles/bill-due-reminders/skills/bill-due-reminders
hermes cron create "0 9 * * 1,4" "Run bill-due-reminders from my bill list in memory." --skill bill-due-reminders
```
Add the lines from `memory.md` to `~/.hermes/memories/MEMORY.md`.

Goose recipe and schedule
```
goose run --recipe goose-recipe.yaml
goose schedule add --schedule-id bill-due-reminders --cron "0 0 9 * * 1,4" --recipe-source ./goose-recipe.yaml
```

Manual copy: put `skills/bill-due-reminders` in `~/.agents/skills/` (Codex, Goose, Cursor) or `~/.claude/skills/` (Claude Code).

## Connectors
This bundle uses no connectors.

License: MIT. Original writing by Drok AI.
