# Bill Due Reminders

Heads-up on bills due before they leave your account. Monday and Thursday at 9:00.

The bill list itself is `memory.md`. Monday and Thursday at 9:00 are `routines.yaml`. Reminder steps are `skills/bill-due-reminders/SKILL.md`. `goose-recipe.yaml` is the Goose reminder. `mcp.json` cannot pay a bill.

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
Amounts come from your list, and no payment is made.

License: MIT. Original writing by Drok AI.
