# Review Reply Drafts

Star rating shapes a reply you can paste back.

Monday at 09:00, once the new reviews are copied in.

Reply craft is in `skills/review-reply-drafts/SKILL.md`. Shop name and sign-off go in `memory.md`. Monday is in `routines.yaml`. `mcp.json` does not log into a review site. Goose loads `goose-recipe.yaml`.

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
No review-site login. Paste the reviews and post the replies yourself.

Drok AI holds the original wording. License: MIT.
