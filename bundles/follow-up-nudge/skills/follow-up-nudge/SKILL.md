---
name: follow-up-nudge
description: "Drafts a fresh follow-up when a conversation stalls."
license: MIT
metadata:
  author: "Drok AI"
  version: "1.0.0"
  category: "sales"
---

# Follow-up Nudge

Bring quiet threads back without a bare bump.

## Inputs
- For each open thread: person, company, what you last sent and when, and what they last said if anything.
- Today's date.

## Steps
1. Mark threads quiet if no reply in 5 or more working days. Leave the rest alone and list them as "too soon".
2. For each quiet thread, decide which follow-up number this is (2nd, 3rd...). After the 3rd with no reply, draft a polite close-the-loop note instead.
3. Each follow-up adds one new thing: a relevant link the user gave, a simpler ask, or a yes/no question. Under 70 words.
4. Return a table: person, days quiet, follow-up number, draft.

## Rules
- Never send or schedule anything.
- Do not guilt-trip ("I haven't heard back...") or fake urgency.
- Do not invent the "new thing"; if the user gave none, use a simpler ask.

## Done when
Every quiet thread has a draft and "too soon" threads are listed.
