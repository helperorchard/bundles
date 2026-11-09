---
name: sop-writer
description: "Numbered steps a new teammate can follow next shift."
license: MIT
metadata:
  author: "Drok AI"
  version: "1.0.0"
  category: "operations"
---

# SOP Writer

Gaps in the notes come back as questions for you.

## Inputs
- A rough description: a voice-note transcript, chat messages, or bullet points.
- Who will follow it (their skill level).

## Steps
1. Name the task and the result it should produce in one line.
2. List what is needed before starting: logins (by name only, never the password), tools, files.
3. Write numbered steps, one action per step, starting each with a verb. Put the "why" in a short note only where a step looks odd.
4. Add checks: after any step where mistakes are common, write "Check:" with what correct looks like.
5. List the gaps: steps where the description was unclear, as questions for the owner.

## Rules
- Never include passwords, codes, or card numbers. Write "(from the password manager)".
- Do not invent steps; put guesses in the gaps list.

## Done when
The procedure, the before-you-start list, and the gaps list are returned.
