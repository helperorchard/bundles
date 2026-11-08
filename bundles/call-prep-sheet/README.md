# Call Prep Sheet

Builds a one-page brief before a sales or partner call from the company's public site and the notes you have.

Category: Sales. Run on demand; no schedule suggested.

Files: `skills/call-prep-sheet/SKILL.md` (the skill), `memory.md` (facts to fill in and keep), `routines.yaml` (schedule), `mcp.json` (connectors), `goose-recipe.yaml`.

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
This bundle uses no connectors.

License: MIT. Original writing by Drok AI.
