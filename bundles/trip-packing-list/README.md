# Trip Packing List

Makes a packing list for a specific trip from the dates, place, weather forecast, and what you will be doing.

Category: Personal. Run on demand; no schedule suggested.

Files: `skills/trip-packing-list/SKILL.md` (the skill), `memory.md` (facts to fill in and keep), `routines.yaml` (schedule), `mcp.json` (connectors), `goose-recipe.yaml`.

## Install

skills.sh CLI (Claude Code, Cursor, Codex, Goose, OpenClaw and more)
```
npx skills add helperorchard/bundles --skill trip-packing-list
```

Hermes Agent
```
hermes skills install helperorchard/bundles/bundles/trip-packing-list/skills/trip-packing-list
```
Add the lines from `memory.md` to `~/.hermes/memories/MEMORY.md`.

Goose recipe
```
goose run --recipe goose-recipe.yaml
```

Manual copy: put `skills/trip-packing-list` in `~/.agents/skills/` (Codex, Goose, Cursor) or `~/.claude/skills/` (Claude Code).

## Connectors
This bundle uses no connectors.

License: MIT. Original writing by Drok AI.
