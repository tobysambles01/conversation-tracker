# Fallback: using a claude.ai Project

Use this only if you can't use Claude Code. Claude Code is the main way to use this template and the one that has been tested most; this route is the fallback and is less tested. Start with `README.md` if you haven't.

A claude.ai Project uses the same files. The difference is that Claude can't change files inside a Project, so after each update you swap in the new versions it gives you (about a minute's work). Your laptop folder holds the master copy of your records.

---

## Setup

1. **Get the files.** Go to https://github.com/tobysambles01/conversation-tracker, click the green **Code** button, then **Download ZIP**. In your Downloads folder, right-click the ZIP and choose **Extract All**, and extract it into your Documents folder. Keep this folder: it holds your master copy of the records.
2. **Fill in your settings.** Open `CLAUDE.md` in a text editor such as Notepad and fill in the square brackets at the top: your name, your team, spelling, how you write dates and your sign-off. Save it.
3. **Create the Project.** On claude.ai, go to **Projects**, then **Create project**. Call it something like "Conversation tracker".
4. **Add the instructions.** Open the Project's instructions and paste in the whole of `CLAUDE.md`.
5. **Upload six files** to the Project's files (knowledge):
   - `records/conversations.md`
   - `records/tracker.csv`
   - `.claude/skills/log/SKILL.md`
   - `.claude/skills/chase/SKILL.md`
   - `.claude/skills/weekly-review/SKILL.md`
   - `.claude/skills/import/SKILL.md`

   The `.claude` folder is hidden. In File Explorer choose View → Show → Hidden items to see it.

   The four skill files share the same file name. That is fine: each one starts with its own name. If claude.ai won't accept a second file with the same name, rename your uploaded copies to `log.md`, `chase.md`, `weekly-review.md` and `import.md` first.
6. **Turn on file creation** if your account offers it (Settings → Capabilities), so Claude can hand you updated files to download.

---

## Using it

In a Project you type the same words as in Claude Code, with or without the slash: `log`, `chase`, `chase Jordan`, `weekly review`, `import`. Everything in `README.md` about the daily routine, the Monday review, asking about the past and importing your history applies, with two differences:

- **Files:** a Project can't see your `notes/` folder. Instead of giving a file name, attach the file to the chat (notes, a transcript, or for `import` the Word document and the sheet export).
- **Saving:** after each change, Claude gives you the new conversation entry and an updated `tracker.csv`. Paste the entry at the end of your own `records/conversations.md`, replace your own `records/tracker.csv` with the new one, then in the Project delete the two old files and upload the new ones. If you skip this, the next chat won't know about the change.

If you change your settings in `CLAUDE.md`, paste the whole file into the Project instructions again.

Projects can't run on a schedule; `automation.md` suggests a calendar reminder instead.
