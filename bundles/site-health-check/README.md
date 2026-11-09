# Site Health Check

Morning pass on load time and basic page text.

Every morning at 08:00 for the pages you listed.

The morning check is `skills/site-health-check/SKILL.md`. Page addresses belong in `memory.md`. `routines.yaml` is 08:00 daily. `mcp.json` needs no account. Goose uses `goose-recipe.yaml`.

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
It opens the page addresses saved in your notes.

Use it under MIT. The author name is Drok AI.
