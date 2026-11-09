# Weekly Meal Plan

A week's dinners that respect your time and your diet. Saturday at 10:00, so the shop can happen the same day.

People, allergies, and busy nights go in `memory.md`. Saturday 10:00 is `routines.yaml`. Planning steps are `skills/weekly-meal-plan/SKILL.md`. `goose-recipe.yaml` is the Saturday run. `mcp.json` does not open a grocer.

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
Fridge contents come from you, and no shop is opened.

License: MIT. Original writing by Drok AI.
