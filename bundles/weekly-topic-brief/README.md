# Weekly Topic Brief

Monday's short note on the topics you asked to follow. Monday at 9:00 is already the chosen time.

The topics live in `memory.md`, Monday 9:00 lives in `routines.yaml`, and the steps live in `skills/weekly-topic-brief/SKILL.md`. `mcp.json` can name a page fetcher. Goose runs `goose-recipe.yaml`.

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

License: MIT. Original writing by Drok AI.
