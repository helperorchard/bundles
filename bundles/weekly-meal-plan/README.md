# Weekly Meal Plan

Plans dinners for the week around your diet, time limits, and what is already in the fridge, plus one shopping list.

Category: Personal. Suggested schedule: every Saturday at 10:00.

Files: `skills/weekly-meal-plan/SKILL.md` (the skill), `memory.md` (facts to fill in and keep), `routines.yaml` (schedule), `mcp.json` (connectors), `goose-recipe.yaml`.

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
This bundle uses no connectors.

License: MIT. Original writing by Drok AI.
