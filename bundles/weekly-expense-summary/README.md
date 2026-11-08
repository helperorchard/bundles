# Weekly Expense Summary

Groups a week of card or bank transactions you paste into categories and flags anything unusual or recurring.

Category: Operations. Suggested schedule: every Sunday at 18:00.

Files: `skills/weekly-expense-summary/SKILL.md` (the skill), `memory.md` (facts to fill in and keep), `routines.yaml` (schedule), `mcp.json` (connectors), `goose-recipe.yaml`.

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
This bundle uses no connectors.

License: MIT. Original writing by Drok AI.
