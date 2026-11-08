# Newsletter Draft

Rough links and notes become one short issue.

Thursday at 15:00, once the week's links are in.

Issue writing is `skills/newsletter-draft/SKILL.md`. The name and sign-off live in `memory.md`. Thursday's nudge is `routines.yaml`. `mcp.json` does not mail anyone. Goose: see `goose-recipe.yaml`.

## Install

skills.sh CLI (Claude Code, Cursor, Codex, Goose, OpenClaw and more)
```
npx skills add helperorchard/bundles --skill newsletter-draft
```

Hermes Agent
```
hermes skills install helperorchard/bundles/bundles/newsletter-draft/skills/newsletter-draft
hermes cron create "0 15 * * 4" "Ask me for this week's notes and links, then run newsletter-draft." --skill newsletter-draft
```
Add the lines from `memory.md` to `~/.hermes/memories/MEMORY.md`.

Goose recipe and schedule
```
goose run --recipe goose-recipe.yaml
goose schedule add --schedule-id newsletter-draft --cron "0 0 15 * * 4" --recipe-source ./goose-recipe.yaml
```

Manual copy: put `skills/newsletter-draft` in `~/.agents/skills/` (Codex, Goose, Cursor) or `~/.claude/skills/` (Claude Code).

## Connectors
No sending service. You get the draft and you mail it.

Covered by the MIT license. The author to name is Drok AI.
