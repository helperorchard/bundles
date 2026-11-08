# Meeting Agenda Builder

Builds a timed agenda from the topics people sent in, with an owner and the decision needed for each item.

Category: Operations. Suggested schedule: every Sunday at 16:00 (before a Monday meeting).

Files: `skills/meeting-agenda-builder/SKILL.md` (the skill), `memory.md` (facts to fill in and keep), `routines.yaml` (schedule), `mcp.json` (connectors), `goose-recipe.yaml`.

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
This bundle uses no connectors.

License: MIT. Original writing by Drok AI.
