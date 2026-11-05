---
name: import
description: Import the manager's full history from their old Word document (.docx) and Google Sheet (exported as .csv) into conversations.md and tracker.csv, in batches, flagging duplicates and unclear owners for the manager to confirm. Never edits, moves or deletes the original files. Use when the manager types /import or asks to bring in their old notes or old tracker.
---

# Import history

This skill backfills both records from the manager's existing Word document of meeting notes and their Google Sheet of actions. The whole history comes across, oldest first, in batches the manager approves one at a time. The record layouts and the data rules are in CLAUDE.md (the Project instructions, if you are in a claude.ai Project).

**The originals are read only.** Never edit, move, rename or delete the Word document, the .csv export, or anything else in the folders they sit in. If you need a converted copy to read from, make it somewhere temporary and leave the originals as they are.

## 1. Ask three things first

Ask these together, in one message:

1. **Where is the Word document?** It should be saved as .docx. (In Claude Code, the manager can drag the file into the window to paste its location. In a Project, they attach it to the chat.)
2. **Where is the Google Sheet export?** In Google Sheets: File → Download → Comma-separated values (.csv). If the sheet has several tabs, each tab downloads separately; ask which tabs matter.
3. **Should dropped or cancelled actions come across?** Either keep them, with Status `dropped`, so the history is complete (suggest this), or leave them out.

## 2. Check what is already in the records

Read `conversations.md` and `tracker.csv`. If there are already real entries (anything other than C-0000 and A-0000), say how many and that imported items will be checked against them for duplicates. Imported items get new IDs carrying on from the highest in use.

If an earlier import was interrupted, find the latest imported conversation (Source ends "(imported from Word document)") and offer to carry on from the next date.

## 3. Read the originals

- **Word document:** in a Project, read the attachment. In Claude Code, if you can't read a .docx directly, extract its text into a temporary file outside this folder using whatever is available on the computer. If that is not possible, ask the manager to open the document in Word and use File → Save a Copy → Plain Text (.txt), keeping the original.
- **Sheet export:** read the .csv. Work out which column holds what: person, action, date raised, due date, original or first due date, status, date completed or closed, last chased, notes, and anything else.

## 4. Report what you found and agree the ground rules

Before writing anything, show the manager a short survey and ask them to confirm or correct it:

- **Meetings found** in the Word document: how many, and the date range.
- **Rows found** in the sheet: how many, and how many are open, done and dropped by their wording.
- **Column mapping:** which sheet column goes to which tracker column. Anything that doesn't fit goes into Notes.
- **Status mapping:** each status word used in the sheet and whether it becomes `open`, `done` or `dropped`. Ask about any you can't place.
- **Names:** every person named, with how often, and suggested merges ("Jordan", "Jordan E." and "JE" → Jordan Ellis). Ask about any that could be more than one person. Do not invent surnames; if only a first name is ever used, keep the first name.
- **Date format:** whether dates are written month first (11/03/2025, usual in the US) or day first (03/11/2025). If the documents could be read either way, ask.
- **Batch size:** suggest a size, such as one quarter or about 25 meetings at a time, oldest first.

## 5. Import one batch at a time

For each batch:

1. **Conversations:** one entry per meeting in the Word document, in the layout from CLAUDE.md. Source is "typed notes (imported from Word document)". Logged is today's date. Put the original notes, in full and unaltered, under "Notes as written", and write a short Summary. Nothing from the document is dropped.
2. **Commitments:** pull out each promise from the notes, as in the log skill, and give each a tracker row.
3. **Sheet rows:** for each sheet row in this batch's date range, look for the same action among the commitments just pulled out (same person, similar wording, close dates). If it matches, fill the tracker row from both and link it to that conversation. If not, add it with Source conversation "Imported from sheet".
4. **Due dates:** Due is the latest due date the records give. Original due is the first one you can find: an "original deadline" column in the sheet if there is one, or the earliest due date mentioned in the notes, or else the same as Due. If the action has no due date at all, leave both blank.
5. **Closed actions:** set Status from the agreed mapping. For done or dropped rows, fill Date closed with the best date available: a completion date in the sheet, or the date of the meeting where the notes say it was finished. If there is none, leave Date closed blank and add `date closed not recorded` to Notes (not a `[check]`: old history often has no dates, and it only matters for recent weeks). Add a note in the standard wording too. Leave out dropped actions if the manager asked you to.
6. **Flags:** anything uncertain gets `[check]` in Notes with the reason, so it can be found later:
   - `[check] possible duplicate of A-0123`: the same action appears twice (twice in the sheet, or in the sheet and the notes in ways you couldn't match for certain, or already in the records). Do not merge these without the manager's say-so.
   - `[check] owner unclear: "we'll get the deck to finance"`: no clear owner. Person is "Unclear".
   - `[check] date unclear`: a due date that couldn't be worked out.
7. **Preview:** show a batch summary rather than every line: the date range, the counts of new conversations, new actions, done, dropped and still open, and then every flagged item listed in full with a suggested answer. Offer to show the full detail. Ask "Save this batch?"
8. **Save** when the manager says yes, as described under "Saving changes" in CLAUDE.md. Apply any answers they gave to the flags and remove the `[check]` from those. Then move on to the next batch.

## 6. Finish

When every batch is in, report:

- totals imported: conversations, actions, and how many are open, done and dropped;
- how many items are still marked `[check]`, and that the manager can ask "show me everything marked check" at any time;
- any actions still open that are more than six months old, asking whether to keep them open, mark them dropped, or go through them one by one;
- a reminder that the original Word document and sheet are untouched and are worth keeping as a backup.

Never send anything to anyone as part of an import.
