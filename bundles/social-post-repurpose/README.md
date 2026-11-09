# Social Post Repurpose

Stretch a blog, talk, or script across the places you post. Open it whenever a piece is finished.

Your channels are written in `memory.md`. `routines.yaml` stays empty until you have a finished piece. The rewrite is `skills/social-post-repurpose/SKILL.md`. Goose has `goose-recipe.yaml`. `mcp.json` does not log into a network.

## Install

skills.sh CLI (Claude Code, Cursor, Codex, Goose, OpenClaw and more)
```
npx skills add helperorchard/bundles --skill social-post-repurpose
```

Hermes Agent
```
hermes skills install helperorchard/bundles/bundles/social-post-repurpose/skills/social-post-repurpose
```
Add the lines from `memory.md` to `~/.hermes/memories/MEMORY.md`.

Goose recipe
```
goose run --recipe goose-recipe.yaml
```

Manual copy: put `skills/social-post-repurpose` in `~/.agents/skills/` (Codex, Goose, Cursor) or `~/.claude/skills/` (Claude Code).

## Connectors
Posts wait until you publish them on your own accounts.

License: MIT. Original writing by Drok AI.
