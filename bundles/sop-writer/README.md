# SOP Writer

Turns a messy description of how you do a task into a numbered step-by-step procedure someone new could follow.

Category: Operations. Run on demand; no schedule suggested.

Files: `skills/sop-writer/SKILL.md` (the skill), `memory.md` (facts to fill in and keep), `routines.yaml` (schedule), `mcp.json` (connectors), `goose-recipe.yaml`.

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
This bundle uses no connectors.

License: MIT. Original writing by Drok AI.
