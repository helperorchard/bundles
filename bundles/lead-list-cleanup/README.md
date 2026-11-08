# Lead List Cleanup

Tidies a messy lead list you paste in: merges duplicates, fixes name and company formats, and flags rows missing key fields.

Category: Sales. Run on demand; no schedule suggested.

Files: `skills/lead-list-cleanup/SKILL.md` (the skill), `memory.md` (facts to fill in and keep), `routines.yaml` (schedule), `mcp.json` (connectors), `goose-recipe.yaml`.

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
This bundle uses no connectors.

License: MIT. Original writing by Drok AI.
