
    __( O)>  ● new session · openrouter openrouter/free
   \____)    20261109_12 · /workspace/skill-bundles
     L L     goose is ready

  ────────────────────────────────────────
  ▸ load_skill
    name: invoice-chaser-drafts


  ────────────────────────────────────────
  ▸ shell
    command: ls -la /workspace/skill-bundles 2>/dev/null | head -50

# Loaded Skill: invoice-chaser-drafts (skill)

Writes polite, firm payment reminder drafts for overdue invoices, stepped by how late each one is. Never sends.

## Content

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
total 116
drwxr-xr-x   5 box box  4096 Nov  9 14:38 .
drwxr-xr-x. 85 box box 69632 Nov  9 10:53 ..
drwxr-xr-x   8 box box  4096 Nov  9 14:12 .git
-rw-r--r--   1 box box    40 Nov  8 14:37 LICENSE
-rw-r--r--   1 box box  5119 Nov  8 15:38 README.md
drwxr-xr-x  26 box box  4096 Nov  8 15:37 bundles
-rw-r--r--   1 box box  2619 Nov  9 14:37 cloudflare_call_prep_sheet.md
-rw-------   1 box box  4600 Nov  9 14:18 content_calendar_helperorchard.md
-rw-r--r--   1 box box  1279 Nov  9 14:38 first_touch_draft_maya_chen.md
drwxr-xr-x   4 box box  4096 Nov  9 14:15 runs### Invoice Drafts

**1. Acme Co**  
**Subject:** Payment Reminder: INV-101 - $1200 due 2026-10-20  

Dear [Contact Name],  

We noticed invoice INV-101 for $1200, due on 2026-10-20, is 20 days overdue. Please arrange payment at your earliest convenience. Let us know your expected payment date.  

Payment details: bank transfer.  

Thank you,  
[Your Name/Company]  

**2. Beta LLC**  
**Subject:** Final Reminder: INV-098 - $450 due 2026-09-15  

Dear [Contact Name],  

This is a final reminder for invoice INV-098 for $450, due on 2026-09-15, which is 55 days overdue. According to our net 30 payment terms, this is well beyond the agreed timeframe. Please arrange payment immediately or confirm a new payment date.  

Payment details: bank transfer.  

We will pause new work until payment is received.  

Best regards,  
[Your Name/Company]  

---

### Summary Table

| Client     | Amount | Days Overdue | Tone Used       |
|------------|--------|--------------|-----------------|
| Acme Co    | $1200  | 20           | clear reminder  |
| Beta LLC   | $450   | 55           | firm            |

Loading recipe: Invoice Chaser Drafts
Description: Writes polite, firm payment reminder drafts for overdue invoices, stepped by how late each one is. Never sends.

