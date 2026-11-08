# Habit Check-in

Mark today's habits and keep the streak honest. Every evening at 21:00.

The habits and the streak live in `memory.md`. 21:00 every day is `routines.yaml`. Check-in steps are `skills/habit-check-in/SKILL.md`. Evening Goose runs use `goose-recipe.yaml`. `mcp.json` needs no tracker app.

## Install

skills.sh CLI (Claude Code, Cursor, Codex, Goose, OpenClaw and more)
```
npx skills add helperorchard/bundles --skill habit-check-in
```

Hermes Agent
```
hermes skills install helperorchard/bundles/bundles/habit-check-in/skills/habit-check-in
hermes cron create "0 21 * * *" "Run habit-check-in for today." --skill habit-check-in
```
Add the lines from `memory.md` to `~/.hermes/memories/MEMORY.md`.

Goose recipe and schedule
```
goose run --recipe goose-recipe.yaml
goose schedule add --schedule-id habit-check-in --cron "0 0 21 * * *" --recipe-source ./goose-recipe.yaml
```

Manual copy: put `skills/habit-check-in` in `~/.agents/skills/` (Codex, Goose, Cursor) or `~/.claude/skills/` (Claude Code).

## Connectors
Answers are typed in the chat at the end of the day.

License: MIT. Original writing by Drok AI.
