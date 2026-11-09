# Trip Packing List

What to pack for this trip, based on weather and plans. Make it a few days before you leave.

Must-haves and your home plug go in `memory.md`. `routines.yaml` has no repeat, because trips are occasional. Packing steps are `skills/trip-packing-list/SKILL.md`. `goose-recipe.yaml` is the Goose version. `mcp.json` books nothing.

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
A public weather page is read for the city you name.

License: MIT. Original writing by Drok AI.
