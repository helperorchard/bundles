# Proposal Outline

Scope and timing laid out from the notes you took. Write it once the call is over.

Rates and terms belong in `memory.md`. There is no clock in `routines.yaml`. Outline steps are `skills/proposal-outline/SKILL.md`. Goose reads `goose-recipe.yaml`. `mcp.json` does not file the proposal.

## Install

skills.sh CLI (Claude Code, Cursor, Codex, Goose, OpenClaw and more)
```
npx skills add helperorchard/bundles --skill proposal-outline
```

Hermes Agent
```
hermes skills install helperorchard/bundles/bundles/proposal-outline/skills/proposal-outline
```
Add the lines from `memory.md` to `~/.hermes/memories/MEMORY.md`.

Goose recipe
```
goose run --recipe goose-recipe.yaml
```

Manual copy: put `skills/proposal-outline` in `~/.agents/skills/` (Codex, Goose, Cursor) or `~/.claude/skills/` (Claude Code).

## Connectors
The outline waits with you until you decide to send it.

License: MIT. Original writing by Drok AI.
