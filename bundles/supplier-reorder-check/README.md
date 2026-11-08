# Supplier Reorder Check

Items to reorder, grouped by the supplier you buy from. Thursday at 16:00 leaves time before Friday orders.

Reorder points and suppliers live in `memory.md`. Thursday 16:00 is `routines.yaml`. Counting steps are `skills/supplier-reorder-check/SKILL.md`. `goose-recipe.yaml` stops at the list. `mcp.json` does not sign into a wholesaler.

## Install

skills.sh CLI (Claude Code, Cursor, Codex, Goose, OpenClaw and more)
```
npx skills add helperorchard/bundles --skill supplier-reorder-check
```

Hermes Agent
```
hermes skills install helperorchard/bundles/bundles/supplier-reorder-check/skills/supplier-reorder-check
hermes cron create "0 16 * * 4" "Ask me for today's stock counts, then run supplier-reorder-check." --skill supplier-reorder-check
```
Add the lines from `memory.md` to `~/.hermes/memories/MEMORY.md`.

Goose recipe and schedule
```
goose run --recipe goose-recipe.yaml
goose schedule add --schedule-id supplier-reorder-check --cron "0 0 16 * * 4" --recipe-source ./goose-recipe.yaml
```

Manual copy: put `skills/supplier-reorder-check` in `~/.agents/skills/` (Codex, Goose, Cursor) or `~/.claude/skills/` (Claude Code).

## Connectors
Stock counts are typed by you, and no order is placed.

License: MIT. Original writing by Drok AI.
