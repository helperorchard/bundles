# Supplier Reorder Check

Compares your stock counts with reorder points and drafts the purchase list per supplier. Does not place orders.

Category: Operations. Suggested schedule: every Thursday at 16:00.

Files: `skills/supplier-reorder-check/SKILL.md` (the skill), `memory.md` (facts to fill in and keep), `routines.yaml` (schedule), `mcp.json` (connectors), `goose-recipe.yaml`.

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
This bundle uses no connectors.

License: MIT. Original writing by Drok AI.
