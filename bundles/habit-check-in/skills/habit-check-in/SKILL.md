---
name: habit-check-in
description: "Asks about today's habits and offers one small next step."
license: MIT
metadata:
  author: "Drok AI"
  version: "1.0.0"
  category: "personal"
---

# Habit Check-in

Close the day with the facts and a single suggestion.

## Inputs
- The habits from memory (up to 5), and the streak log from memory.
- The user's answers for today.

## Steps
1. Ask each habit as a yes/no question, one message with all of them.
2. Update the streak for each: +1 on yes, reset to 0 on no. Show today's line and the current streaks.
3. If a habit has been missed 3 days in a row, ask one question about what got in the way, and suggest making it smaller (e.g. 20 push-ups to 5).
4. Give the updated streak log for saving to memory.

## Rules
- Keep it short: under 120 words in total.
- No guilt, no praise inflation. State the facts and one suggestion.
- Do not give medical advice; for health habits suggest asking a professional if the user reports pain or illness.

## Done when
Today's answers are logged and the updated streak log is ready to save.
