---
name: meeting-actions
description: "Names the tasks a meeting actually left behind."
license: MIT
metadata:
  author: "Drok AI"
  version: "1.0.0"
---

# Meeting Actions

Read the notes once, then name every task someone owns.

## Steps
1. Read the whole text once before writing anything.
2. List decisions: things the group agreed on. One line each.
3. List action items. For each, give:
   - the task, starting with a verb
   - the owner, only if a name is said or clearly implied; otherwise "owner not set"
   - the due date, only if one is said; otherwise "no date"
4. List open questions that nobody answered.
5. End with a two-sentence summary of the meeting.

## Rules
- Do not invent owners, dates, or decisions.
- Quote the exact words when a line is unclear, and mark it "unclear".
- Do not send the result to anyone. Return it in the chat.

## Done when
Every task in the notes appears once, with an owner and date or the "not set" label.
