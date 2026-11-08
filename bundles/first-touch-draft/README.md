# First Touch Draft

Your first hello stays a draft until you choose to send it. Weekdays at 10:00 only remind you to write one.

Put your offer in `memory.md`. `routines.yaml` nudges you at 10:00 on weekdays. The writing rules are `skills/first-touch-draft/SKILL.md`. `goose-recipe.yaml` is for Goose, and `mcp.json` leaves mail untouched.

## Install

skills.sh CLI (Claude Code, Cursor, Codex, Goose, OpenClaw and more)
```
npx skills add helperorchard/bundles --skill first-touch-draft
```

Hermes Agent
```
hermes skills install helperorchard/bundles/bundles/first-touch-draft/skills/first-touch-draft
# or from a local copy:
cp -r skills/first-touch-draft ~/.hermes/skills/
hermes cron create "0 10 * * 1-5" "Ask me for today's prospects, then run first-touch-draft for each one." --skill first-touch-draft
```
Add the lines from `memory.md` to `~/.hermes/memories/MEMORY.md`.

OpenClaw
```
openclaw skills install ./skills/first-touch-draft
```

Codex, Goose, Cursor (shared folder)
```
mkdir -p ~/.agents/skills && cp -r skills/first-touch-draft ~/.agents/skills/
```

Claude Code
```
mkdir -p ~/.claude/skills && cp -r skills/first-touch-draft ~/.claude/skills/
```

Goose recipe and schedule
```
goose run --recipe goose-recipe.yaml
goose schedule add --schedule-id first-touch-draft --cron "0 0 10 * * 1-5" --recipe-source ./goose-recipe.yaml
```
(Goose cron includes a seconds field, hence the leading `0`.)

## Connectors
Finished drafts wait in the chat for you to send.

License: MIT. Original writing by Drok AI.
