# Habit Check-in

Runs a short end-of-day check-in on the habits you chose, keeps a running streak, and gives one small suggestion.

Category: Personal. Suggested schedule: every day at 21:00.

Files: `skills/habit-check-in/SKILL.md` (the skill), `memory.md` (facts to fill in and keep), `routines.yaml` (schedule), `mcp.json` (connectors), `goose-recipe.yaml`.

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
This bundle uses no connectors.

License: MIT. Original writing by Drok AI.
