# Social Post Repurpose

Rewrites one piece you already made (blog post, video script, talk) into posts sized for each of your channels.

Category: Marketing. Run on demand; no schedule suggested.

Files: `skills/social-post-repurpose/SKILL.md` (the skill), `memory.md` (facts to fill in and keep), `routines.yaml` (schedule), `mcp.json` (connectors), `goose-recipe.yaml`.

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
This bundle uses no connectors.

License: MIT. Original writing by Drok AI.
