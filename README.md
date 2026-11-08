# HelperOrchard bundles

Original, MIT-licensed helper bundles for people who are not developers. Each bundle is one job: a skill (agentskills.io `SKILL.md`), memory notes to fill in, a suggested schedule, connector notes, and a Goose recipe. They work in Hermes Agent, Goose, Claude Code, Cursor, Codex, OpenClaw and other tools that read `SKILL.md`.

Anything that could message people only writes drafts. Nothing here sends, posts, pays, or buys.

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
| [weekly-topic-brief](bundles/weekly-topic-brief) | Weekly sourced roundup on topics or competitors, a link for every claim |
| [review-reply-drafts](bundles/review-reply-drafts) | Drafts calm, specific replies to customer reviews you paste in, matched to star rating. Drafts only; you post them. |
| [competitor-price-watch](bundles/competitor-price-watch) | Checks the public price pages of competitors you list and reports what changed since the last check. |
| [content-calendar](bundles/content-calendar) | Plans the next two weeks of posts from your goals and past posts, with a date, channel, and hook for each. |
| [newsletter-draft](bundles/newsletter-draft) | Turns your rough notes and links from the week into a short, readable newsletter draft with a subject line. |
| [social-post-repurpose](bundles/social-post-repurpose) | Rewrites one piece you already made (blog post, video script, talk) into posts sized for each of your channels. |

### Sales

| Bundle | What it does |
|---|---|
| [first-touch-draft](bundles/first-touch-draft) | Two short outreach drafts from facts you supply; never sends |
| [invoice-chaser-drafts](bundles/invoice-chaser-drafts) | Writes polite, firm payment reminder drafts for overdue invoices, stepped by how late each one is. Never sends. |
| [lead-list-cleanup](bundles/lead-list-cleanup) | Tidies a messy lead list you paste in: merges duplicates, fixes name and company formats, and flags rows missing key fields. |
| [follow-up-nudge](bundles/follow-up-nudge) | Looks at your list of open conversations and drafts a short, useful follow-up for each one that has gone quiet. Drafts only. |
| [call-prep-sheet](bundles/call-prep-sheet) | Builds a one-page brief before a sales or partner call from the company's public site and the notes you have. |
| [proposal-outline](bundles/proposal-outline) | Turns your call notes into a structured proposal outline with scope, timeline, price options, and open questions. |

### Operations

| Bundle | What it does |
|---|---|
| [site-health-check](bundles/site-health-check) | Daily uptime and basic SEO check for your pages |
| [meeting-actions](bundles/meeting-actions) | Notes or transcript to decisions, actions, owners, dates |
| [inbox-triage-summary](bundles/inbox-triage-summary) | Sorts the emails you paste or export into reply-today, this-week, read-later, and ignore, with a one-line reason each. |
| [weekly-expense-summary](bundles/weekly-expense-summary) | Groups a week of card or bank transactions you paste into categories and flags anything unusual or recurring. |
| [supplier-reorder-check](bundles/supplier-reorder-check) | Compares your stock counts with reorder points and drafts the purchase list per supplier. Does not place orders. |
| [meeting-agenda-builder](bundles/meeting-agenda-builder) | Builds a timed agenda from the topics people sent in, with an owner and the decision needed for each item. |
| [sop-writer](bundles/sop-writer) | Turns a messy description of how you do a task into a numbered step-by-step procedure someone new could follow. |

### Personal

| Bundle | What it does |
|---|---|
| [job-post-watch](bundles/job-post-watch) | Checks the careers pages you list for new roles that match your title and location, and reports only the new ones. |
| [trip-packing-list](bundles/trip-packing-list) | Makes a packing list for a specific trip from the dates, place, weather forecast, and what you will be doing. |
| [bill-due-reminders](bundles/bill-due-reminders) | Lists the bills due in the next 10 days from your saved bill list, with amounts and which are on autopay. |
| [weekly-meal-plan](bundles/weekly-meal-plan) | Plans dinners for the week around your diet, time limits, and what is already in the fridge, plus one shopping list. |
| [habit-check-in](bundles/habit-check-in) | Runs a short end-of-day check-in on the habits you chose, keeps a running streak, and gives one small suggestion. |

Each bundle folder has: `skills/<slug>/SKILL.md`, `memory.md`, `routines.yaml`, `mcp.json`, `goose-recipe.yaml`, `README.md`.
