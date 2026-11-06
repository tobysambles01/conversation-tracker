# Changelog

All notable changes to this template are listed here, newest first.

## 1.5.0 · 2026-11-06

- `setup-guide-mac.html`: a Mac version of the setup guide, with the same nine sections and "you will see" checks. It covers installing the app from a .dmg, Safari unzipping the download, showing hidden files with Cmd+Shift+full stop, allowing Claude to access the Documents folder (and the System Settings fix if refused), TextEdit's Make Plain Text, Save As .docx in Word for Mac, Cmd shortcuts, and a check on iCloud syncing of Documents.
- `setup-guide.html` and `setup-guide-mac.html` each point to the other at the top.
- `README.md`: names both guides under Setup and in the folder table; the setup and update steps note the Mac differences.

## 1.4.0 · 2026-11-05

- `.gitignore`: ignores everything in `notes/` apart from its README. `records/` can't be ignored because the blank templates ship in it, so `README.md` now says a copy in use must never be connected to git, and the ZIP is the only route given (the `git clone` hint is gone).
- `project-setup.md`: the claude.ai Project setup moved here from `README.md`, marked as the fallback and less tested, with how to attach files in place of `notes/`. `README.md` has a one-line pointer and lists the file; `setup-guide.html` mentions it where Claude Code can't be enabled.

## 1.3.0 · 2026-11-05

- `setup-guide.html`: a step-by-step setup guide for the manager, readable on a phone and printable, with a "you will see" check on every step.
- `notes/`: a folder for the manager's own files (notes, transcripts, the import exports) with a short README. `/log` accepts a file name from it and records the file name as the source; `/import` looks there for the Word document and sheet.
- `weekly-review`: "Slipped this week" (the deadline moved or passed during the week) is now separate from "Running late" (slipped earlier, still open). A move counts in the week of its dated note, so a move after the Sunday belongs to the next review. `[check]` rows are left out of the team review and listed for the manager. An empty tracker is reported instead of reviewed.
- `log`: warns when a meeting with the same date and people is already logged; handles material with no commitments; reads numeric dates using a new "Dates in my notes" setting.
- `chase`: says so when nobody has anything open; skips rows whose owner is still unclear.
- `import`: suggests a backup of `records/` first; a concrete way to read a .docx when nothing else is installed.
- `CLAUDE.md`: Original due may be corrected only at the manager's explicit request, with a note; a missing tracker column is added empty and the manager told; records are re-read right before each change; `git add`, `commit` and `push` are never run.
- `README.md`: Windows walk-through with Download ZIP and Extract All; pick the model; an "Updating the template" section that keeps `records/` and `notes/`; what to do if something goes wrong.

## 1.2.0 · 2026-11-05

- `records/tracker.csv`: new **Original due** column after Due. It is set the first time an action gets a due date and never changed after; Due is the current date. The example row shows it filled.
- `weekly-review`: an open action is Slipped when Due is later than Original due, or when it is overdue. Both dates are shown: "Was due Fri 30 Oct, now Fri 6 Nov."
- `log` and `import`: write Original due.
- Re-ran the weekly review on the invented test data to confirm.

## 1.1.0 · 2026-11-04

- `records/tracker.csv`: new **Date closed** column after Status, filled when an action becomes done or dropped and cleared if it is reopened. The example row shows it filled.
- `weekly-review`: uses Date closed to decide what was done or dropped in the week. Describes the week as it stood on its Sunday, so a review run later in the week no longer loses actions closed after the Sunday or includes actions raised after it. The totals line now gives "open in total" instead of a confusing "still open" count, and moved deadlines show both dates.
- `log` and `import`: write Date closed. `log` now works out past days ("sent it Weds") backwards from the conversation date.
- `chase`: the notes for the manager mention their own overdue actions.
- `README.md`: after editing the instructions or a skill, start a new Claude Code session.
- Tested with invented data: `/log` for two people, `/chase` and `/weekly-review`.

## 1.0.0 · 2026-11-04

First version.

- `CLAUDE.md`: settings, the two records and their layouts, how changes are saved in Claude Code and in a claude.ai Project, the four skills, rules about data (drafts only, nothing sent, show before saving, nothing deleted), answering questions about history, and the output formats.
- `records/conversations.md` and `records/tracker.csv`: blank templates, each with one invented example.
- Skills in `.claude/skills/`: `log`, `chase`, `weekly-review` and `import`.
- `README.md`: setup in Claude Code and in a claude.ai Project, the daily and Monday routines, asking about history, and importing a Word document and Google Sheet.
- `automation.md`: how to schedule the Monday review and draft messages into Outlook or Slack. Described only; nothing is switched on.
