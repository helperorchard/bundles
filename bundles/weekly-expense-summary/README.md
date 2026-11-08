# Weekly Expense Summary

Seven days of spend, sorted and compared to budget.

Sunday at 18:00, with the week's charges pasted in.

Spending rules are `skills/weekly-expense-summary/SKILL.md`. Budget and nicknames go in `memory.md`. Sunday evening is `routines.yaml`. `mcp.json` is not a bank. Goose runs `goose-recipe.yaml`.

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
No bank link. Paste the transactions from your statement.

MIT license, no extra catch. Author credit: Drok AI.
