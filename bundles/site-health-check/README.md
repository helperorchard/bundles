# Site Health Check

Morning pass over uptime and obvious problems on your pages. 8:00 each morning is the standing check.

Drop your page links into `memory.md`. The 8:00 habit is written in `routines.yaml`, the checks themselves in `skills/site-health-check/SKILL.md`, the Goose version in `goose-recipe.yaml`, and `mcp.json` stays quiet because a login is not required.

## Install

skills.sh CLI (Claude Code, Cursor, Codex, Goose, OpenClaw and more)
```
npx skills add helperorchard/bundles --skill site-health-check
```

Hermes Agent
```
hermes skills install helperorchard/bundles/bundles/site-health-check/skills/site-health-check
# or from a local copy:
cp -r skills/site-health-check ~/.hermes/skills/
hermes cron create "0 8 * * *" "Run site-health-check on the sites in memory and send me the table." --skill site-health-check
```
Add the lines from `memory.md` to `~/.hermes/memories/MEMORY.md`.

OpenClaw
```
openclaw skills install ./skills/site-health-check
```

Codex, Goose, Cursor (shared folder)
```
mkdir -p ~/.agents/skills && cp -r skills/site-health-check ~/.agents/skills/
```

Claude Code
```
mkdir -p ~/.claude/skills && cp -r skills/site-health-check ~/.claude/skills/
```

Goose recipe and schedule
```
goose run --recipe goose-recipe.yaml
goose schedule add --schedule-id site-health-check --cron "0 0 8 * * *" --recipe-source ./goose-recipe.yaml
```
(Goose cron includes a seconds field, hence the leading `0`.)

## Connectors
Public pages are opened directly, and you never sign in.

License: MIT. Original writing by Drok AI.
