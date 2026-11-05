---
name: weekly-review
description: Draft the Monday weekly review for the manager's team covering the previous Monday to Sunday - what each person committed to, what was done, what slipped and what is still open - in plain text to paste into email or Slack. Read-only; never sends. Use when the manager types /weekly-review or asks for the Monday review or a weekly summary.
---

# Weekly review

This skill drafts the review the manager sends to their team each Monday. It reads the records and changes nothing. The weekly review format and the data rules are in CLAUDE.md (the Project instructions, if you are in a claude.ai Project).

## 1. Work out the week

- By default, cover the most recent full week from Monday to Sunday that has ended. Run on a Monday, that is the seven days ending yesterday.
- If the manager names a different week ("the week of 13 October"), use that Monday to Sunday.
- State the dates at the top of the review.

## 2. Work out who is in it

- Everyone listed under "Team" in Settings, in that order.
- The manager too, if "Include my own actions in the weekly review" is yes.
- If the Team setting is still blank, ask for the names before going on.

## 3. Sort each person's actions

Use `tracker.csv`. Leave out the example row A-0000 and any row whose Notes contain `[private]`.

Describe the week as it stood at the end of its Sunday, even if you are running the review later:

- Leave out actions with a Date raised after that Sunday.
- Treat an action whose Date closed is after that Sunday as still open for this review.

Then put each action in exactly one group, using the first group it fits:

1. **Done:** Status `done` and Date closed is within the week. If it was also raised this week, add "(new this week)".
2. **Dropped:** Status `dropped` and Date closed is within the week.
3. **Slipped:** Status `open` and either Due is later than Original due (the deadline has been pushed back), or Due is on or before the Sunday that ends the week (it is overdue). Show both dates when they differ: "Was due Fri 30 Oct, now Fri 6 Nov." When they are the same: "Was due Fri 30 Oct."
4. **Committed this week:** Status `open` and Date raised is within the week.
5. **Still open:** every other open action.

## 4. Write the review

Use the weekly review format in CLAUDE.md:

- One line at the top with the totals across everyone in the review: new commitments (the Committed this week group plus anything marked "new this week"), done, slipped, and open in total (every action still open at the end of the week, whichever group it is in).
- One section per person, name in capitals. Inside it: Done, Committed this week, Slipped, Still open, Dropped. Leave out any heading with nothing under it. If a person had nothing at all, write "Nothing logged this week."
- Each action on one line, starting with a verb, with its due date written like "Fri 7 Nov".
- Plain text only, so it pastes cleanly into email or Slack.
- Do not copy anything from the Notes column into the review.

## 5. Notes for the manager

After the review, separated by a line, add a short note only the manager sees, if any of these apply:

- actions marked `[check]` that are included and may need confirming first;
- open actions with no due date;
- team members with nothing logged for several weeks;
- people with actions who are not in the Team setting (they are left out of the review).

## Never send

The review is a draft. Do not send or post it anywhere. If the manager asks for it as an Outlook or Slack draft and a connector that creates drafts is available, create a draft only and tell the manager where it is.
