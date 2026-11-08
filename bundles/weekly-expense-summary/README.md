# Weekly Expense Summary

Where the week's card charges went, in plain groups. Sunday at 18:00, once those charges are pasted in.

Budget and the alert amount go in `memory.md`. Sunday 18:00 is `routines.yaml`. Sorting steps are `skills/weekly-expense-summary/SKILL.md`. `goose-recipe.yaml` is the Sunday run. `mcp.json` never sees a bank login.

## Install

skills.sh CLI (Claude Code, Cursor, Codex, Goose, OpenClaw and more)
```
npx skills add helperorchard/bundles --skill weekly-expense-summary
```

Hermes Agent
```
hermes skills install helperorchard/bundles/bundles/weekly-expense-summary/skills/weekly-expense-summary
hermes cron create "0 18 * * 0" "Ask me to paste this week's transactions, then run weekly-expense-summary." --skill weekly-expense-summary
```
Add the lines from `memory.md` to `~/.hermes/memories/MEMORY.md`.

Goose recipe and schedule
```
goose run --recipe goose-recipe.yaml
goose schedule add --schedule-id weekly-expense-summary --cron "0 0 18 * * 0" --recipe-source ./goose-recipe.yaml
```

Manual copy: put `skills/weekly-expense-summary` in `~/.agents/skills/` (Codex, Goose, Cursor) or `~/.claude/skills/` (Claude Code).

## Connectors
Only the statement you paste is used for the totals.

License: MIT. Original writing by Drok AI.
