# Review Reply Drafts

Drafts calm, specific replies to customer reviews you paste in, matched to star rating. Drafts only; you post them.

Category: Marketing. Suggested schedule: every Monday at 09:00.

Files: `skills/review-reply-drafts/SKILL.md` (the skill), `memory.md` (facts to fill in and keep), `routines.yaml` (schedule), `mcp.json` (connectors), `goose-recipe.yaml`.

## Install

skills.sh CLI (Claude Code, Cursor, Codex, Goose, OpenClaw and more)
```
npx skills add helperorchard/bundles --skill review-reply-drafts
```

Hermes Agent
```
hermes skills install helperorchard/bundles/bundles/review-reply-drafts/skills/review-reply-drafts
hermes cron create "0 9 * * 1" "Remind me to paste this week's new reviews, then run review-reply-drafts on them." --skill review-reply-drafts
```
Add the lines from `memory.md` to `~/.hermes/memories/MEMORY.md`.

Goose recipe and schedule
```
goose run --recipe goose-recipe.yaml
goose schedule add --schedule-id review-reply-drafts --cron "0 0 9 * * 1" --recipe-source ./goose-recipe.yaml
```

Manual copy: put `skills/review-reply-drafts` in `~/.agents/skills/` (Codex, Goose, Cursor) or `~/.claude/skills/` (Claude Code).

## Connectors
This bundle uses no connectors.

License: MIT. Original writing by Drok AI.
