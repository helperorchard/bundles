---
name: invoice-chaser-drafts
description: "Writes polite, firm payment reminder drafts for overdue invoices, stepped by how late each one is. Never sends."
license: MIT
metadata:
  author: "Drok AI"
  version: "1.0.0"
  category: "sales"
---

# Invoice Chaser Drafts

Use this when someone has unpaid invoices and wants reminder emails ready to send themselves.

## Inputs
- For each invoice: client name, contact name, invoice number, amount with currency, due date, and any earlier reminders sent.
- Today's date.

## Steps
1. Work out days overdue for each invoice. Skip any not yet due and list them as "not due".
2. Pick the tone by lateness:
   - 1-14 days: friendly nudge, assume it slipped through.
   - 15-44 days: clear reminder, restate amount and due date, ask for a payment date.
   - 45+ days: firm, mention the payment terms from memory and what happens next per memory (e.g. pause work). No threats beyond that.
3. Write a subject line and a body under 120 words for each, with invoice number, amount, and due date exactly as given.
4. Add the payment details line from memory.
5. Give a short table: client, amount, days overdue, tone used.

## Rules
- Never send, schedule, or open an email tool to deliver these.
- Never add late fees or interest unless memory says the contract includes them.
- Copy numbers exactly; do not round.

## Done when
Each overdue invoice has a draft and the summary table is shown.
