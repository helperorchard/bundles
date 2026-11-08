# First Touch Draft

Drafts a short, specific first outreach message for one prospect from facts you supply. Never sends anything.

Files: `skills/first-touch-draft/SKILL.md` (the skill), `memory.md` (facts to keep), `routines.yaml` (schedule), `mcp.json` (connectors), `goose-recipe.yaml`.

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
This bundle uses no connectors.

License: MIT. Original writing by Drok AI.
