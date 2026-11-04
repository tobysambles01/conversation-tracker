---
name: chase
description: Draft one chase message per person listing their open actions and due dates, ready for the manager to paste into Slack or email or read out. Updates "Last chased" only for the people the manager says they will chase. Never sends anything. Use when the manager types /chase, asks who they need to chase, or asks for a chase list for a named person.
---

# Chase open actions

This skill drafts chase messages from the tracker. It never sends them. The chase message format and the data rules are in CLAUDE.md (the Project instructions, if you are in a claude.ai Project).

## 1. Decide who to chase

- If the manager named people ("/chase Jordan", "chase Sam and Priya"), chase only them.
- If they said "overdue only" or similar, include only overdue actions.
- Otherwise, chase everyone with at least one open action, except the manager.
- Ignore the example row A-0000.
- If a first name could match more than one person, ask which one.

## 2. Gather each person's actions

From `tracker.csv`, take every row for that person with Status `open`. Sort them:

1. overdue (Due is before today), oldest due date first;
2. then by due date;
3. then actions with no due date.

Rows marked `[check]` are still unconfirmed. Leave them out of the message and list them for the manager instead.

## 3. Draft the messages

Use the chase message format in CLAUDE.md, one message per person:

- Friendly and short. No blame, no pressure words.
- Each action on its own line with its due date written like "Fri 7 Nov", and "(overdue)" if it has passed.
- For actions with no date, ask whether a date can be set.
- Include only that person's actions. Never mention anyone else's actions, and never copy text from the Notes column into the message.
- End with the sign-off from Settings.

## 4. Add notes for the manager

Above the drafts, add a short note only the manager sees, covering anything useful, for example:

- "Jordan was last chased on Mon 3 Nov, two days ago."
- "A-0017 for Sam is marked [check] and is left out of the message."
- "Priya has nothing open."

## 5. Update "Last chased"

After the drafts, ask: "Which of these will you send? Say 'all', or name the people, and I'll set Last chased to today on the actions in their messages."

When the manager answers, show which action IDs will change, then save as described under "Saving changes" in CLAUDE.md. Change only the Last chased column on those rows.

## Never send

Do not send, post or schedule any message. If the manager asks you to put the drafts into Outlook or Slack and a connector that creates drafts is available, create drafts only, one per person, and tell the manager where they are. If the only option is to send, stop and say so; the manager can copy the text instead.
