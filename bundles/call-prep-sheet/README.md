# Call Prep Sheet

Skim this page in the five minutes before you dial. Open it before the conversation, whenever that is.

Your offer and the usual objections go in `memory.md`. `routines.yaml` has no standing time. The one-page steps are `skills/call-prep-sheet/SKILL.md`. Goose takes `goose-recipe.yaml`. `mcp.json` adds no contact book.

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
Facts come from the company's public site and your notes.

License: MIT. Original writing by Drok AI.
