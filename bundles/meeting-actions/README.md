# Meeting Actions

After the meeting, the follow-ups in one list.

Paste notes whenever a meeting ends. Friday at 16:00 can sweep for owners and dates still blank.

How notes get sorted is `skills/meeting-actions/SKILL.md`. Name and date habits go in `memory.md`. The Friday sweep is `routines.yaml`. `mcp.json` has nothing to connect. Goose runs `goose-recipe.yaml`.

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
No calendar connection. Paste the notes or the transcript.

Original work of Drok AI, offered under the MIT license.
