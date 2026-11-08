# Social Post Repurpose

Same story, trimmed for every place you post.

When a blog, script, or talk is finished. No weekly slot.

Reshaping rules are `skills/social-post-repurpose/SKILL.md`. Channels and banned phrases live in `memory.md`. `routines.yaml` leaves the timing to you. `mcp.json` has no social login. `goose-recipe.yaml` is the Goose side.

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
No social account is attached. You copy the posts over.

MIT applies here. Drok AI wrote what you are reading.
