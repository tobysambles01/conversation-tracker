# Conversation tracker

Log every meeting or conversation once. Claude keeps a record of what was said and who promised what, and from that it drafts your chase messages and your Monday review for the team.

- **Log** a meeting by pasting your typed notes or a transcript. Claude writes it up, picks out every commitment, and updates your tracker. It shows you every change before saving.
- **Chase** people with one ready-to-send message each, listing what they owe and when it is due.
- **Review** the week every Monday: what each person committed to, what got done, what is still open and what slipped.
- **Ask** about the past: "What did Jordan say about the budget?" or "What has Sam committed to since March?"
- **Import** your existing Word document and Google Sheet so your whole history comes across.

Claude never sends anything. Everything it writes for other people is a draft for you to send yourself.

This is a template. Every name in it is invented.

---

## What's in the folder

| File | What it is |
|---|---|
| `README.md` | This guide. |
| `CLAUDE.md` | The instructions Claude follows. You fill in a few settings at the top. |
| `records/conversations.md` | Your log of conversations, one entry each. |
| `records/tracker.csv` | Your list of actions, one row each. Opens in Excel. |
| `.claude/skills/` | Four folders (log, chase, weekly-review, import), each holding a `SKILL.md` file with Claude's step-by-step instructions. |
| `automation.md` | How to have the Monday review drafted for you automatically, and how to have chase messages drafted into Outlook or Slack. |
| `CHANGELOG.md` | What has changed in this template. |

The `.claude` folder starts with a dot, so your computer may hide it. On Windows, in File Explorer choose View → Show → Hidden items. On a Mac, in Finder press Command + Shift + full stop.

---

## Before you start: your records are private

Once you start using this, the files in `records/` will hold notes about your staff. Keep them on your work laptop, or wherever your company says staff notes belong. Do not upload your copy to GitHub or any other public site.

---

## Setup, option 1: Claude Code (recommended)

Claude Code runs on your laptop and works directly on the files in this folder, so your records update themselves when you approve a change.

You will need Claude Code on your laptop and switched on for your Enterprise account. If you don't have it, ask your IT team or Claude admin.

1. **Get the files.** Either:
   - **Download:** on the GitHub page, click the green **Code** button, then **Download ZIP**. Unzip it somewhere sensible, such as your Documents folder, and call the folder `conversation-tracker`. Or:
   - **Clone:** open a terminal and run:
     ```
     git clone https://github.com/tobysambles01/conversation-tracker.git
     ```
2. **Open Claude Code in the folder.** Either:
   - in the Claude desktop app, open the **Code** tab and choose the `conversation-tracker` folder; or
   - in a terminal, go to the folder and type `claude`.

   The first time, sign in with your work account.
3. **Fill in your settings.** Type: `Help me fill in the settings in CLAUDE.md`. Claude asks for your name, your team's names, your preferred spelling and your sign-off, then writes them in. (You can also open `CLAUDE.md` in any text editor and fill in the square brackets yourself.)
4. **Import your history** if you have some. See "Importing your history" below.

From then on you use four commands. Type them where you talk to Claude:

| Type | To |
|---|---|
| `/log` | Log a meeting or conversation. Paste your notes or transcript after it. |
| `/chase` | Draft chase messages for everyone with open actions. Add a name to chase one person: `/chase Jordan`. |
| `/weekly-review` | Draft the Monday review for last week. |
| `/import` | Bring in your old Word document and Google Sheet. |

---

## Setup, option 2: a claude.ai Project

Use this if you can't use Claude Code. It uses the same files. The difference is that Claude can't change files inside a Project, so after each update you swap in the new versions it gives you (about a minute's work).

1. **Get the files.** On the GitHub page, click the green **Code** button, then **Download ZIP**, and unzip it on your laptop. Keep this folder: it holds your master copy of the records.
2. **Fill in your settings.** Open `CLAUDE.md` in a text editor and fill in the square brackets at the top: your name, your team, spelling and sign-off. Save it.
3. **Create the Project.** On claude.ai, go to **Projects**, then **Create project**. Call it something like "Conversation tracker".
4. **Add the instructions.** Open the Project's instructions and paste in the whole of `CLAUDE.md`.
5. **Upload six files** to the Project's files (knowledge):
   - `records/conversations.md`
   - `records/tracker.csv`
   - `.claude/skills/log/SKILL.md`
   - `.claude/skills/chase/SKILL.md`
   - `.claude/skills/weekly-review/SKILL.md`
   - `.claude/skills/import/SKILL.md`

   The four skill files share the same file name. That is fine: each one starts with its own name. If claude.ai won't accept a second file with the same name, rename your uploaded copies to `log.md`, `chase.md`, `weekly-review.md` and `import.md` first.
6. **Turn on file creation** if your account offers it (Settings → Capabilities), so Claude can hand you updated files to download.

In a Project you type the same words, with or without the slash: `log`, `chase`, `chase Jordan`, `weekly review`, `import`.

**After each change**, Claude gives you the new conversation entry and an updated `tracker.csv`. Paste the entry at the end of your own `conversations.md`, replace your own `tracker.csv` with the new one, then in the Project delete the two old files and upload the new ones. If you skip this, the next chat won't know about the change.

---

## Your daily routine

**After each meeting or conversation**, type `/log` and paste your notes or the transcript. Rough notes are fine.

Claude will:

1. say whether it read your text as typed notes or a transcript;
2. ask about anything unclear, such as "we'll look into it" (who is "we"?) or "end of the month" (which month?);
3. show you the new entry, new actions and any changes to existing ones;
4. save only when you reply "yes".

If someone mentions they've finished something, put it in your notes. Claude will spot it and mark the action done.

**When you want to chase**, type `/chase` (or `/chase Sam`). You get one message per person, ready to paste into Slack or email or to read out in person. Tell Claude which ones you are sending and it records today as the date you last chased them. It never sends anything itself.

---

## Your Monday routine

Type `/weekly-review`. Claude drafts the review of the previous Monday to Sunday for each person in your team:

- what they **committed to** that week;
- what they got **done**;
- what **slipped** past its due date;
- what is **still open**.

It is plain text, so it pastes cleanly into an email or a Slack message. Read it, edit it if you like, and send it yourself. Underneath, Claude adds a few notes just for you, such as actions with no due date.

To have the review waiting for you at 8am on Mondays, see `automation.md`.

Any action marked `[private]` in the tracker stays out of the review. Claude suggests this for anything personal.

---

## Asking about the past

Ask in plain words. For example:

- What did Jordan say about the hiring plan?
- What has Sam committed to since 1 March?
- What's overdue?
- When did Priya first raise the rota problem?

Claude answers only from your records and tells you which conversation each point comes from, for example "3 Nov (C-0012)". If the records don't say, it tells you so rather than guessing.

---

## Importing your history

Do this once, at the start. It brings your whole history across.

1. **Get your Word document ready.** It should be a .docx file. If it's another format, open it in Word and use File → Save a Copy → Word Document (.docx).
2. **Export your Google Sheet.** In Google Sheets: File → Download → Comma-separated values (.csv). If you use more than one tab, download each one you need.
3. **Type `/import`.** Claude asks you three things:
   - where the Word document is (in Claude Code, you can drag the file into the window);
   - where the sheet export is;
   - whether to keep actions you dropped or cancelled. Keeping them, marked "dropped", gives you the complete history.
4. **Check the survey.** Before writing anything, Claude shows what it found: how many meetings and actions, how your columns and status words map across, and the names it found, with suggestions for merging variations ("Jordan", "Jordan E.", "JE"). Correct anything that's wrong.
5. **Approve each batch.** Claude imports a few months at a time, oldest first. For each batch it shows a summary and lists anything it's unsure of, such as possible duplicates or actions with no clear owner. Answer what you can and say "yes" to save. Anything you leave unanswered is marked `[check]`, so you can come back to it by asking "show me everything marked check".

Your original Word document and sheet are never changed, moved or deleted. Keep them as a backup.

A long history can take a while. If you stop part way, type `/import` again later and Claude offers to carry on from where it stopped.

---

## Good to know

- **Nothing is ever sent.** Claude only drafts. You send.
- **You approve every change** to your records before it is saved.
- **Nothing is deleted.** Finished actions are marked `done` or `dropped` and stay in the tracker as history.
- **Opening the tracker in Excel:** viewing is fine. If you save it from Excel, Excel may change the dates to its own format. Save it as CSV and check that dates still read like 2026-11-07, or ask Claude to make the change instead.
- **The examples:** the entries C-0000 and A-0000 are invented examples. Claude ignores them. Delete them whenever you like.
- **Spelling:** this guide uses British English. To have Claude write your drafts in US spelling, change "Spelling for drafts" in the settings at the top of `CLAUDE.md` to "US English" (and, in a Project, paste the updated instructions in again).
- **Backups:** keep a copy of the `records` folder somewhere your company approves, such as your work OneDrive.
- **Automation:** `automation.md` explains how to have the Monday review drafted automatically and how to have chase messages drafted into Outlook or Slack. Nothing in it is switched on unless you set it up.
