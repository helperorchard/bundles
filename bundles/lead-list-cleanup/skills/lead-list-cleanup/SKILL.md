---
name: lead-list-cleanup
description: "Straightens a messy contact list without adding people."
license: MIT
metadata:
  author: "Drok AI"
  version: "1.0.0"
  category: "sales"
---

# Lead List Cleanup

Hand in the spreadsheet and take back one clean list.

## Inputs
- The list as pasted rows or CSV text. Columns can be in any order.

## Steps
1. Identify the columns: name, email, company, role, source, notes. Ask only if you cannot tell.
2. Normalise: trim spaces, capitalise names, lowercase emails, remove "Inc."-style noise only for matching (keep it in output).
3. Find duplicates by same email, or same name plus same company. Merge them, keeping the newest non-empty value per field and joining notes.
4. Flag rows with no email, an email that is not shaped like name@domain, or a free-mail address when the list is meant to be business leads.
5. Return: the clean list as CSV, then counts (rows in, rows out, merged, flagged), then the flagged rows with the reason.

## Rules
- Do not look people up or add data that was not in the list.
- Do not delete flagged rows; mark them.
- Do not email or add anyone to any tool.

## Done when
The clean CSV, the counts, and the flagged rows are returned.
