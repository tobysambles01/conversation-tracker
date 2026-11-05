# Changelog

All notable changes to this template are listed here, newest first.

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
