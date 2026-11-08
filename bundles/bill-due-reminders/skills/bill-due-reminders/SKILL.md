---
name: bill-due-reminders
description: "Lists the bills due in the next 10 days from your saved bill list, with amounts and which are on autopay."
license: MIT
metadata:
  author: "Drok AI"
  version: "1.0.0"
  category: "personal"
---

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
