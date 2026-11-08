# Competitor Price Watch

See which rival prices moved since you last looked. Look again every Monday at 8:00.

Save the price links and the last prices in `memory.md`. Monday 8:00 is `routines.yaml`. Reading steps are `skills/competitor-price-watch/SKILL.md`. `goose-recipe.yaml` is the Monday run in Goose. `mcp.json` has no shop login.

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
Only the price links you saved are opened.

License: MIT. Original writing by Drok AI.
