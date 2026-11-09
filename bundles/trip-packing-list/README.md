# Trip Packing List

Clothes and gear for the trip you actually booked.

A few days before you leave, once the dates are firm. No repeating schedule.

Packing judgment is `skills/trip-packing-list/SKILL.md`. Must-haves live in `memory.md`. `routines.yaml` does not repeat. Weather may use the web; `mcp.json` still has no booking account. Goose: `goose-recipe.yaml`.

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
Nothing here books travel. Weather can use the open web.

This is Drok AI's writing, shared under MIT.
