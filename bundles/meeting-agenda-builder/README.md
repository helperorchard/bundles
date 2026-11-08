# Meeting Agenda Builder

Topics in, a timed agenda out.

Sunday at 16:00, ahead of a Monday meeting.

Agenda building is `skills/meeting-agenda-builder/SKILL.md`. Length and regular people belong in `memory.md`. Sunday is recorded in `routines.yaml`. `mcp.json` sends no invites. `goose-recipe.yaml` is for Goose.

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
No invite tool. The agenda stays in the chat for you to share.

Drok AI published this under the MIT license.
