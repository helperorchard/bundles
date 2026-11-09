
    __( O)>  ● new session · openrouter openrouter/free
   \____)    20261109_3 · /workspace/skill-bundles
     L L     goose is ready

  ────────────────────────────────────────
  ▸ load_skill
    name: bill-due-reminders

# Loaded Skill: bill-due-reminders (skill)

Lists the bills due in the next 10 days from your saved bill list, with amounts and which are on autopay.

## Content

# Bill Due Reminders

Use this so no bill slips by.

## Inputs
- The bill list from memory: name, usual amount, due day of month, autopay yes/no.
- Today's date.

## Steps
1. For each bill, work out the next due date from the due day. If the day does not exist in a month (e.g. 31st), use the last day.
2. Keep bills due in the next 10 days.
3. Sort by due date. Mark autopay bills "check balance" and manual ones "pay by hand".
4. Total the amounts due in the window.
5. List any bill in memory with no due day as "missing date".

## Rules
- Never pay, log in, or move money.
- Amounts are the usual amounts from memory; say "usual" so the user checks the real bill.

## Done when
The sorted 10-day list, the total, and missing-date bills are shown.

  ────────────────────────────────────────
  ▸ run
    skill: bill-due-reminders

Tool 'run' is not available.

Here's your bill rundown for **today, 2026-11-09** (window: Nov 9 – Nov 19).

## Bills due in the next 10 days

| Due Date | Bill | Amount (usual) | Action |
|---|---|---|---|
| Nov 12 | Internet | $60 | autopay — **check balance** |
| Nov 15 | Electric | $90 | manual — **pay by hand** |

**Total due in window: $150**

## Just outside the window
- **Phone** — $45, due Nov 20 (manual, pay by hand) — one day past the 10-day window.
- **Rent** — $1,400, due Dec 1 (autopay, check balance) — not yet.

## Missing date
- **Storage unit** — $75 (manual) — no due day on file. Please add it so it doesn't slip.

Reminder: amounts are the usuals from memory — verify against the real bills before paying.

Loading recipe: Bill Due Reminders
Description: Lists the bills due in the next 10 days from your saved bill list, with amounts and which are on autopay.

