# Proposal Outline

Outline ends wherever your call notes stop.

Right after a discovery call, while the notes are still fresh. No weekly slot.

Outline steps are `skills/proposal-outline/SKILL.md`. Rate and terms go in `memory.md`. `routines.yaml` does not pick a day. `mcp.json` contacts nobody. `goose-recipe.yaml` runs the same job in Goose.

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
Paste the call notes when you want the outline.

These notes and the skill are MIT-licensed, from Drok AI.
