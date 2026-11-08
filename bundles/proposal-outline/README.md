# Proposal Outline

Turns your call notes into a structured proposal outline with scope, timeline, price options, and open questions.

Category: Sales. Run on demand; no schedule suggested.

Files: `skills/proposal-outline/SKILL.md` (the skill), `memory.md` (facts to fill in and keep), `routines.yaml` (schedule), `mcp.json` (connectors), `goose-recipe.yaml`.

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
This bundle uses no connectors.

License: MIT. Original writing by Drok AI.
