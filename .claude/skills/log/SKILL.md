---
name: log
description: Log a meeting or conversation from typed notes or a pasted transcript. Writes the conversation entry, adds or updates actions in the tracker, asks about unclear owners or dates, and shows every change before saving. Use when the manager types /log, says "log this", or pastes notes or a transcript from a meeting.
---

# Log a conversation

This skill turns notes or a transcript from one meeting or conversation into a conversation entry and tracker updates. The record layouts, the change preview format and the data rules are in CLAUDE.md (the Project instructions, if you are in a claude.ai Project). Follow them exactly.

## 1. Get the material

- If the manager typed or pasted text after the command, that is the material. If not, ask them to paste their notes or the transcript, or to give the file's location.
- One conversation per log. If the material clearly covers two separate conversations, say so and offer to log them one after the other.

## 2. Work out what it is

Decide whether it is **typed notes** or a **transcript**, and say which in the preview.

- A transcript usually has speaker names at the start of lines, timestamps, or long back-and-forth wording ("Yeah, so I think…").
- Typed notes are usually short, abbreviated and written by one person.
- If you can't tell, ask.

## 3. Read the records

Read `conversations.md` and `tracker.csv`. Note:

- the highest conversation ID and the highest action ID in use, ignoring C-0000 and A-0000, so new IDs carry on from them;
- every open action belonging to anyone in this conversation, so you can spot updates;
- how people's names are already written, so you use the same form.

## 4. Draft the entry

- **Date:** the date of the conversation. Take it from the material if it is there. If not, ask; suggest today's date.
- **Title:** a short plain description, such as "Weekly one-to-one with Sam Okafor" or "Budget review with finance".
- **Who:** everyone who took part, full names in the form already used in the records, the manager included.
- **Summary:** three to six sentences on what was discussed and decided.
- **Notes as written:** typed notes exactly as written; for a transcript, the key points with speaker names and short quotes for decisions and promises.
- **Commitments:** every promise to do something, by anyone, including the manager. Write each one starting with a verb. Work out due dates from the conversation date ("by Friday" means the Friday on or after that date). Things already done work backwards: "sent it Weds" means the Wednesday on or before the conversation date.
- **Updates to earlier actions:** anything in the material that finishes, drops or moves the deadline of an open action. Only match an existing action when it is clearly the same thing; if you are not sure, ask.

## 5. Ask about anything unclear

Before you show the preview, ask about anything you would otherwise have to guess, all in one message, numbered, each with your best suggestion. For example:

- Owner unclear: "we'll sort the venue", "someone needs to call IT", "the team will review it".
- Name unclear: a first name or initials that could be more than one person, or a name not yet in the records.
- Date unclear: "soon", "next week", "end of the month", "before the offsite", or no date at all.
- Possible match to an existing action that might be different.
- Anything sensitive that you plan to leave out or suggest marking `[private]`.

If the manager says an action has no date, leave Due blank. If they say to skip a question, leave the action out or mark it `[check]`, whichever they choose.

## 6. Show the preview

Use the change preview format from CLAUDE.md. Include the new conversation, new actions with their IDs, changed actions showing old → new (with the Date closed for anything closed), and anything you left out. End with: Reply "yes" to save, or tell me what to change.

If the manager asks for changes, make them and show the preview again.

## 7. Save

Only after the manager says yes, save as described under "Saving changes" in CLAUDE.md:

- Add the conversation entry at the end of `conversations.md`, ending with a `---` line.
- Add new rows at the end of `tracker.csv`.
- New rows have Status `open` and a blank Date closed.
- For changed rows: update Status or Due, and add a note in the standard wording, for example `2026-11-06: done (C-0015)` or `2026-11-06: due moved from 2026-11-07 to 2026-11-14 (C-0015)`.
- Whenever Status becomes `done` or `dropped`, fill Date closed: the date it was actually finished or dropped if the material says ("sent it on Tuesday"), otherwise the conversation date. If a closed action is reopened, set Status back to `open`, clear Date closed and add a `reopened` note.
- Check the tracker is still valid CSV with ten columns on every row.

Then confirm in one line, for example: "Saved C-0015 with 2 new actions (A-0042, A-0043) and 2 updates (A-0029, A-0031)."

Never send anything to anyone as part of logging.
