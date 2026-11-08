# Call Prep Sheet

Read their site and your notes before you dial.

For sales and partner calls, whenever one is on the books.

`skills/call-prep-sheet/SKILL.md` holds the steps. What you sell goes in `memory.md`. `routines.yaml` has no weekly job. `mcp.json` stays unused, and Goose uses `goose-recipe.yaml`.

## Install

skills.sh CLI (Claude Code, Cursor, Codex, Goose, OpenClaw and more)
```
npx skills add helperorchard/bundles --skill call-prep-sheet
```

Hermes Agent
```
hermes skills install helperorchard/bundles/bundles/call-prep-sheet/skills/call-prep-sheet
```
Add the lines from `memory.md` to `~/.hermes/memories/MEMORY.md`.

Goose recipe
```
goose run --recipe goose-recipe.yaml
```

Manual copy: put `skills/call-prep-sheet` in `~/.agents/skills/` (Codex, Goose, Cursor) or `~/.claude/skills/` (Claude Code).

## Connectors
The company site and your notes are enough.

Drok AI wrote this, and the MIT license lets you reuse it.
