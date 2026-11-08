# Weekly Meal Plan

Five dinners shaped by the week you described.

Saturday at 10:00, after a look in the fridge.

Dinner planning is `skills/weekly-meal-plan/SKILL.md`. People, allergies, and busy nights go in `memory.md`. Saturday morning is `routines.yaml`. `mcp.json` has no grocery account. `goose-recipe.yaml` is the Goose recipe.

## Install

skills.sh CLI (Claude Code, Cursor, Codex, Goose, OpenClaw and more)
```
npx skills add helperorchard/bundles --skill weekly-meal-plan
```

Hermes Agent
```
hermes skills install helperorchard/bundles/bundles/weekly-meal-plan/skills/weekly-meal-plan
hermes cron create "0 10 * * 6" "Ask me what's in the fridge, then run weekly-meal-plan." --skill weekly-meal-plan
```
Add the lines from `memory.md` to `~/.hermes/memories/MEMORY.md`.

Goose recipe and schedule
```
goose run --recipe goose-recipe.yaml
goose schedule add --schedule-id weekly-meal-plan --cron "0 0 10 * * 6" --recipe-source ./goose-recipe.yaml
```

Manual copy: put `skills/weekly-meal-plan` in `~/.agents/skills/` (Codex, Goose, Cursor) or `~/.claude/skills/` (Claude Code).

## Connectors
No grocery account. The shopping list is only a list.

Drok AI created the text. MIT is how it is shared.
