# Meeting Actions

The follow-ups a meeting actually left on the table. Friday at 16:00 catches blanks that are still open.

How you like names and dates is `memory.md`. `routines.yaml` remembers Friday at 16:00. Read `skills/meeting-actions/SKILL.md` for the method, `goose-recipe.yaml` if you use Goose, and `mcp.json` for the note that your calendar is not hooked up.

## Install

skills.sh CLI (Claude Code, Cursor, Codex, Goose, OpenClaw and more)
```
npx skills add helperorchard/bundles --skill meeting-actions
```

Hermes Agent
```
hermes skills install helperorchard/bundles/bundles/meeting-actions/skills/meeting-actions
# or from a local copy:
cp -r skills/meeting-actions ~/.hermes/skills/
hermes cron create "0 16 * * 5" "List any action items from this week's meeting-actions results that still say 'owner not set' or 'no date'." --skill meeting-actions
```
Add the lines from `memory.md` to `~/.hermes/memories/MEMORY.md`.

OpenClaw
```
openclaw skills install ./skills/meeting-actions
```

Codex, Goose, Cursor (shared folder)
```
mkdir -p ~/.agents/skills && cp -r skills/meeting-actions ~/.agents/skills/
```

Claude Code
```
mkdir -p ~/.claude/skills && cp -r skills/meeting-actions ~/.claude/skills/
```

Goose recipe and schedule
```
goose run --recipe goose-recipe.yaml
goose schedule add --schedule-id meeting-actions --cron "0 0 16 * * 5" --recipe-source ./goose-recipe.yaml
```
(Goose cron includes a seconds field, hence the leading `0`.)

## Connectors
Notes are pasted, so the calendar is left alone.

License: MIT. Original writing by Drok AI.
