# Bill Due Reminders

Ten days of bills, including the ones on autopay.

Home life. Check Monday and Thursday at 09:00.

Read the skill at `skills/bill-due-reminders/SKILL.md`, keep the bill rows in `memory.md`, the clock in `routines.yaml`, connector notes in `mcp.json`, and the Goose run in `goose-recipe.yaml`.

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
No outside account. It reads the bill list in your notes.

The MIT license applies. Drok AI wrote the original text.
