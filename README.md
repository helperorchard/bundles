# HelperOrchard bundles

Small helpers for people who do not write code. Each folder does one everyday job, and you can run it in Hermes Agent, Goose, Claude Code, Cursor, Codex, OpenClaw, or another tool that reads a `SKILL.md` file. The license is MIT.

If the job could reach another person, you get a draft to send yourself. Nothing in here sends a message, posts, pays, or places an order.

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

Each bundle's own page has its install lines, the time it suggests, and the notes you fill in.

## Bundles

### Marketing

| Bundle | What it does |
|---|---|
| [weekly-topic-brief](bundles/weekly-topic-brief) | Monday roundup of fresh news, with a link on every line. |
| [review-reply-drafts](bundles/review-reply-drafts) | Calm replies for reviews you paste, ready for you to post. |
| [competitor-price-watch](bundles/competitor-price-watch) | Spots price changes on the competitor pages you save. |
| [content-calendar](bundles/content-calendar) | Two weeks of post ideas tied to one goal. |
| [newsletter-draft](bundles/newsletter-draft) | Turns the week's scraps into a newsletter you can edit. |
| [social-post-repurpose](bundles/social-post-repurpose) | Cuts one finished piece into posts for each channel. |

### Sales

| Bundle | What it does |
|---|---|
| [first-touch-draft](bundles/first-touch-draft) | First notes for one prospect, built only from your facts. |
| [invoice-chaser-drafts](bundles/invoice-chaser-drafts) | Polite payment reminders that get firmer as invoices age. |
| [lead-list-cleanup](bundles/lead-list-cleanup) | Tidies a pasted lead list and marks the gaps. |
| [follow-up-nudge](bundles/follow-up-nudge) | Short follow-ups for chats that have gone quiet. |
| [call-prep-sheet](bundles/call-prep-sheet) | One page of public facts before a sales call. |
| [proposal-outline](bundles/proposal-outline) | An outline you can turn into the proposal after the call. |

### Operations

| Bundle | What it does |
|---|---|
| [site-health-check](bundles/site-health-check) | Sees whether your pages load and look sound for search. |
| [meeting-actions](bundles/meeting-actions) | Finds who owes what after the meeting ends. |
| [inbox-triage-summary](bundles/inbox-triage-summary) | Sorts a pasted inbox so you know what needs a reply. |
| [weekly-expense-summary](bundles/weekly-expense-summary) | Shows where this week's pasted charges actually went. |
| [supplier-reorder-check](bundles/supplier-reorder-check) | Buy list for stock that slipped under your reorder point. |
| [meeting-agenda-builder](bundles/meeting-agenda-builder) | Timed agenda built from topics people already sent in. |
| [sop-writer](bundles/sop-writer) | Numbered steps a new person could follow tomorrow. |

### Personal

| Bundle | What it does |
|---|---|
| [job-post-watch](bundles/job-post-watch) | New matching roles on the careers pages you follow. |
| [trip-packing-list](bundles/trip-packing-list) | Packing list shaped by the forecast and your plans. |
| [bill-due-reminders](bundles/bill-due-reminders) | Bills due in the next ten days, including autopay. |
| [weekly-meal-plan](bundles/weekly-meal-plan) | Weeknight dinners that use what is already in the fridge. |
| [habit-check-in](bundles/habit-check-in) | Nightly check on the habits you chose to keep. |

Every folder holds the steps (`skills/<slug>/SKILL.md`), notes you fill in (`memory.md`), a suggested time (`routines.yaml`), connector details (`mcp.json`), a Goose recipe (`goose-recipe.yaml`), and a short page (`README.md`).
