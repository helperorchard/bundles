# Lead List Cleanup

Cleans names and companies in a list you paste. Run it when a spreadsheet lands.

Column habits sit in `memory.md`. `routines.yaml` is empty on purpose. Cleanup steps are `skills/lead-list-cleanup/SKILL.md`. You can hand `goose-recipe.yaml` to Goose. `mcp.json` does not touch a contact book.

## Install

skills.sh CLI (Claude Code, Cursor, Codex, Goose, OpenClaw and more)
```
npx skills add helperorchard/bundles --skill lead-list-cleanup
```

Hermes Agent
```
hermes skills install helperorchard/bundles/bundles/lead-list-cleanup/skills/lead-list-cleanup
```
Add the lines from `memory.md` to `~/.hermes/memories/MEMORY.md`.

Goose recipe
```
goose run --recipe goose-recipe.yaml
```

Manual copy: put `skills/lead-list-cleanup` in `~/.agents/skills/` (Codex, Goose, Cursor) or `~/.claude/skills/` (Claude Code).

## Connectors
Whatever spreadsheet you paste is the entire input.

License: MIT. Original writing by Drok AI.
