# Habit Check-in

End the day by marking habits and keeping score.

An evening ritual, every day at 21:00.

Evening questions are written in `skills/habit-check-in/SKILL.md`. Habits and streaks stay in `memory.md`. `routines.yaml` says 21:00. `mcp.json` is blank on purpose. `goose-recipe.yaml` is there for Goose.

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
No app connection. You answer the questions in chat.

License for this helper is MIT. Author: Drok AI.
