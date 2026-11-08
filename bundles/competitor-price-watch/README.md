# Competitor Price Watch

Checks the public price pages of competitors you list and reports what changed since the last check.

Category: Marketing. Suggested schedule: every Monday at 08:00.

Files: `skills/competitor-price-watch/SKILL.md` (the skill), `memory.md` (facts to fill in and keep), `routines.yaml` (schedule), `mcp.json` (connectors), `goose-recipe.yaml`.

## Install

skills.sh CLI (Claude Code, Cursor, Codex, Goose, OpenClaw and more)
```
npx skills add helperorchard/bundles --skill competitor-price-watch
```

Hermes Agent
```
hermes skills install helperorchard/bundles/bundles/competitor-price-watch/skills/competitor-price-watch
hermes cron create "0 8 * * 1" "Run competitor-price-watch on the pricing pages in memory and show me what changed." --skill competitor-price-watch
```
Add the lines from `memory.md` to `~/.hermes/memories/MEMORY.md`.

Goose recipe and schedule
```
goose run --recipe goose-recipe.yaml
goose schedule add --schedule-id competitor-price-watch --cron "0 0 8 * * 1" --recipe-source ./goose-recipe.yaml
```

Manual copy: put `skills/competitor-price-watch` in `~/.agents/skills/` (Codex, Goose, Cursor) or `~/.claude/skills/` (Claude Code).

## Connectors
This bundle uses no connectors.

License: MIT. Original writing by Drok AI.
