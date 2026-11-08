# Meeting Agenda Builder

Fits everyone's topics into the minutes you actually have. Sunday at 16:00, ahead of a Monday meeting.

Usual length and regular people go in `memory.md`. Sunday 16:00 is `routines.yaml`. Agenda steps are `skills/meeting-agenda-builder/SKILL.md`. `goose-recipe.yaml` is there for Goose. `mcp.json` sends no invite.

## Install

skills.sh CLI (Claude Code, Cursor, Codex, Goose, OpenClaw and more)
```
npx skills add helperorchard/bundles --skill meeting-agenda-builder
```

Hermes Agent
```
hermes skills install helperorchard/bundles/bundles/meeting-agenda-builder/skills/meeting-agenda-builder
hermes cron create "0 16 * * 0" "Ask me for this week's topics, then run meeting-agenda-builder." --skill meeting-agenda-builder
```
Add the lines from `memory.md` to `~/.hermes/memories/MEMORY.md`.

Goose recipe and schedule
```
goose run --recipe goose-recipe.yaml
goose schedule add --schedule-id meeting-agenda-builder --cron "0 0 16 * * 0" --recipe-source ./goose-recipe.yaml
```

Manual copy: put `skills/meeting-agenda-builder` in `~/.agents/skills/` (Codex, Goose, Cursor) or `~/.claude/skills/` (Claude Code).

## Connectors
Topics arrive from you, and the agenda is not mailed out.

License: MIT. Original writing by Drok AI.
