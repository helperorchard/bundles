---
name: meeting-agenda-builder
description: "Builds a timed agenda from the topics people sent in, with an owner and the decision needed for each item."
license: MIT
metadata:
  author: "Drok AI"
  version: "1.0.0"
  category: "operations"
---

# Meeting Agenda Builder

Use this before a team meeting when topics came in from several people.

## Inputs
- Meeting length and attendees.
- Topics, each with who raised it if known.
- Open action items from last time, if any.

## Steps
1. Merge topics that are the same thing said two ways.
2. For each topic, write the decision or output needed ("decide X", "agree owner for Y", "share update on Z").
3. Put decisions first, then updates. Updates that need no discussion go to a "Read before" list instead.
4. Give each item minutes so the total is at most the meeting length minus 5 minutes for wrap-up.
5. Start with a 5-minute check of last meeting's actions if any were given.
6. Return the agenda as a numbered list: time, item, owner, decision needed.

## Rules
- Do not drop a topic silently; anything cut goes under "Parked" with the reason.
- Draft only. Do not send invites or post the agenda.

## Done when
A timed agenda, a read-before list, and a parked list are returned.
