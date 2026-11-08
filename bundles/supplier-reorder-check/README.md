# Supplier Reorder Check

Counts versus reorder points, orders still yours.

Thursday at 16:00, after the shelves have been counted.

Stock rules are `skills/supplier-reorder-check/SKILL.md`. Reorder points and suppliers go in `memory.md`. Thursday afternoon is `routines.yaml`. `mcp.json` does not order goods. `goose-recipe.yaml` is for Goose.

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
No shop system. Give the counts and get a list back.

Written by Drok AI and licensed MIT, so you can adapt it.
