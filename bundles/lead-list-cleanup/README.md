# Lead List Cleanup

Clean contacts back, with gaps marked not deleted.

Any time a messy sales export shows up. No fixed clock.

Cleanup rules live in `skills/lead-list-cleanup/SKILL.md`. Column wishes sit in `memory.md`. `routines.yaml` does not set a clock. `mcp.json` is not a CRM. Run Goose from `goose-recipe.yaml`.

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
No CRM. Paste the sheet and take the clean list back.

MIT license on the whole folder. Words by Drok AI.
