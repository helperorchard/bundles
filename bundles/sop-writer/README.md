# SOP Writer

Steps written so a new helper can do the task tomorrow. Write one while the task is still fresh in your head.

Where you keep procedures is `memory.md`. `routines.yaml` waits until you have a task to explain. Writing steps are `skills/sop-writer/SKILL.md`. Goose uses `goose-recipe.yaml` when you want a recipe. `mcp.json` attaches no document app.

## Install

skills.sh CLI (Claude Code, Cursor, Codex, Goose, OpenClaw and more)
```
npx skills add helperorchard/bundles --skill sop-writer
```

Hermes Agent
```
hermes skills install helperorchard/bundles/bundles/sop-writer/skills/sop-writer
```
Add the lines from `memory.md` to `~/.hermes/memories/MEMORY.md`.

Goose recipe
```
goose run --recipe goose-recipe.yaml
```

Manual copy: put `skills/sop-writer` in `~/.agents/skills/` (Codex, Goose, Cursor) or `~/.claude/skills/` (Claude Code).

## Connectors
You describe the task in your own words, then get steps back.

License: MIT. Original writing by Drok AI.
