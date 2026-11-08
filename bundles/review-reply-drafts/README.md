# Review Reply Drafts

Answer each star rating in your own shop's voice. Start the week at 9:00 by clearing new reviews.

Shop name, signature, and refund rules go in `memory.md`. Monday 9:00 is `routines.yaml`. Reply steps are `skills/review-reply-drafts/SKILL.md`. The Goose copy is `goose-recipe.yaml`. `mcp.json` does not log into the review site.

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
Replies wait for you to paste them onto the review site.

License: MIT. Original writing by Drok AI.
