# HelperOrchard bundles

Everyday helpers for people who do not write software. Each folder does one job: a skill, notes you can fill in, a time it can run, connector notes, and a Goose recipe. Tools that know how to read a skill file can use them, including Hermes Agent, Goose, Claude Code, Cursor, Codex, and OpenClaw.

If a job would message someone, it stops at a draft. Nothing here sends, posts, pays, or buys.

## Install

All bundles with the skills.sh CLI:
```
npx skills add helperorchard/bundles            # pick from a list
npx skills add helperorchard/bundles --skill meeting-actions
```

Hermes Agent:
```
hermes skills install helperorchard/bundles/bundles/<slug>/skills/<slug>
# or add the whole repo as a source, then search it:
hermes skills tap add helperorchard/bundles
hermes skills search <word>
```

Goose: `goose run --recipe bundles/<slug>/goose-recipe.yaml`

Each bundle's README has its own install, schedule, and memory lines.

## Bundles

### Marketing

| Bundle | What it does |
|---|---|
| [weekly-topic-brief](bundles/weekly-topic-brief) | Weekly sourced brief on the topics you care about. |
| [review-reply-drafts](bundles/review-reply-drafts) | Calm review replies matched to the star rating. |
| [competitor-price-watch](bundles/competitor-price-watch) | Price moves on the competitor pages you saved. |
| [content-calendar](bundles/content-calendar) | Next two weeks of posts, with a hook each. |
| [newsletter-draft](bundles/newsletter-draft) | Week's notes turned into a newsletter you can send. |
| [social-post-repurpose](bundles/social-post-repurpose) | One finished piece rewritten for each channel. |

### Sales

| Bundle | What it does |
|---|---|
| [first-touch-draft](bundles/first-touch-draft) | Two short first notes from facts you supply. |
| [invoice-chaser-drafts](bundles/invoice-chaser-drafts) | Payment reminders that firm up as invoices age. |
| [lead-list-cleanup](bundles/lead-list-cleanup) | Tidy a pasted lead list and mark what is missing. |
| [follow-up-nudge](bundles/follow-up-nudge) | Useful follow-ups for threads that went quiet. |
| [call-prep-sheet](bundles/call-prep-sheet) | One-page brief before a sales or partner call. |
| [proposal-outline](bundles/proposal-outline) | Call notes shaped into a proposal you can finish. |

### Operations

| Bundle | What it does |
|---|---|
| [site-health-check](bundles/site-health-check) | Whether your pages are up and easy to find. |
| [meeting-actions](bundles/meeting-actions) | Decisions and tasks taken from meeting notes. |
| [inbox-triage-summary](bundles/inbox-triage-summary) | Today's emails sorted so replies come first. |
| [weekly-expense-summary](bundles/weekly-expense-summary) | Week of card and bank charges, odd ones called out. |
| [supplier-reorder-check](bundles/supplier-reorder-check) | Reorder list grouped by the supplier you buy from. |
| [meeting-agenda-builder](bundles/meeting-agenda-builder) | Timed agenda from topics already in your inbox. |
| [sop-writer](bundles/sop-writer) | Messy task notes turned into steps a newbie can follow. |

### Personal

| Bundle | What it does |
|---|---|
| [job-post-watch](bundles/job-post-watch) | New roles on careers pages you already follow. |
| [trip-packing-list](bundles/trip-packing-list) | Bag checklist for this destination and its weather. |
| [bill-due-reminders](bundles/bill-due-reminders) | Upcoming bills from the list you keep. |
| [weekly-meal-plan](bundles/weekly-meal-plan) | Dinners for the week and one shopping list. |
| [habit-check-in](bundles/habit-check-in) | An evening check-in for habits you chose. |

Inside each bundle you will find `skills/<slug>/SKILL.md`, plus `memory.md`, `routines.yaml`, `mcp.json`, `goose-recipe.yaml`, and `README.md`.
