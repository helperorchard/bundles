# Meeting Actions

Turns meeting notes or a transcript into a clear list of decisions, action items, owners, and due dates. Use after any meeting.

Files: `skills/meeting-actions/SKILL.md` (the skill), `memory.md` (facts to keep), `routines.yaml` (schedule), `mcp.json` (connectors), `goose-recipe.yaml`.

## Install

Hermes Agent
```
hermes skills install <owner>/<repo>/bundles/meeting-actions/skills/meeting-actions
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
This bundle uses no connectors.

License: MIT. Original writing by Drok AI.
