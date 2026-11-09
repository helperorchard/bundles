# SOP Writer

Say how you do it, get a procedure back.

When a task lives in your head and someone else will need it. No fixed day.

Procedure writing is `skills/sop-writer/SKILL.md`. Where files live, and who reads them, goes in `memory.md`. `routines.yaml` has no clock. `mcp.json` is unused. Goose can run `goose-recipe.yaml`.

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
Talk through the task. There is nothing to sign into.

The license is MIT, and Drok AI wrote the bundle.
