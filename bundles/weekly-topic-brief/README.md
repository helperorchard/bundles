# Weekly Topic Brief

Public sources only, and a link sits on every claim.

Monday at 09:00, covering the last seven days.

Brief writing is `skills/weekly-topic-brief/SKILL.md`. Topic names belong in `memory.md`. Monday morning is `routines.yaml`. Optional fetch notes are in `mcp.json`. Goose uses `goose-recipe.yaml`.

## Install

skills.sh CLI (Claude Code, Cursor, Codex, Goose, OpenClaw and more)
```
npx skills add helperorchard/bundles --skill weekly-topic-brief
```

Hermes Agent
```
hermes skills install helperorchard/bundles/bundles/weekly-topic-brief/skills/weekly-topic-brief
# or from a local copy:
cp -r skills/weekly-topic-brief ~/.hermes/skills/
hermes cron create "0 9 * * 1" "Run weekly-topic-brief for the topics in memory." --skill weekly-topic-brief
```
Add the lines from `memory.md` to `~/.hermes/memories/MEMORY.md`.

OpenClaw
```
openclaw skills install ./skills/weekly-topic-brief
```

Codex, Goose, Cursor (shared folder)
```
mkdir -p ~/.agents/skills && cp -r skills/weekly-topic-brief ~/.agents/skills/
```

Claude Code
```
mkdir -p ~/.claude/skills && cp -r skills/weekly-topic-brief ~/.claude/skills/
```

Goose recipe and schedule
```
goose run --recipe goose-recipe.yaml
goose schedule add --schedule-id weekly-topic-brief --cron "0 0 9 * * 1" --recipe-source ./goose-recipe.yaml
```
(Goose cron includes a seconds field, hence the leading `0`.)

## Connectors
Optional connector: the official MCP `fetch` server (`uvx mcp-server-fetch`). See mcp.json. Hermes: add it under `mcp_servers:` in `~/.hermes/config.yaml`; OpenClaw: `openclaw mcp add fetch --command uvx --arg mcp-server-fetch`; Codex: `codex mcp add fetch -- uvx mcp-server-fetch`; Claude Code: `claude mcp add fetch -- uvx mcp-server-fetch`; Cursor: copy into `~/.cursor/mcp.json`.

Share and adapt this under MIT. Name Drok AI as the author.
