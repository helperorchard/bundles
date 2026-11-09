# Competitor Price Watch

Saved pricing pages compared with what you stored.

A Monday 08:00 pass over the pricing pages you saved.

Price checking lives in `skills/competitor-price-watch/SKILL.md`. Links and last prices go in `memory.md`. The Monday job is `routines.yaml`. `mcp.json` does not add a login. Open `goose-recipe.yaml` when you use Goose.

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
No login helper. It opens the public pricing links you stored.

You can reuse this under MIT. Credit the writing to Drok AI.
