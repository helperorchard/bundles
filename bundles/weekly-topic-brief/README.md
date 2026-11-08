# Weekly Topic Brief

Writes a short weekly brief on chosen topics or competitors from recent public web sources, with a link for every claim.

Files: `skills/weekly-topic-brief/SKILL.md` (the skill), `memory.md` (facts to keep), `routines.yaml` (schedule), `mcp.json` (connectors), `goose-recipe.yaml`.

## Install

Hermes Agent
```
hermes skills install <owner>/<repo>/bundles/weekly-topic-brief/skills/weekly-topic-brief
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

License: MIT. Original writing by Drok AI.
