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
| `setup-guide.html` | A step-by-step setup guide you can open in your browser or print. Same content as this guide, one step at a time. |
| `project-setup.md` | The fallback if you can't use Claude Code: setting this up in a claude.ai Project instead. Less tested. |
| `CLAUDE.md` | The instructions Claude follows. You fill in a few settings at the top. |
| `records/conversations.md` | Your log of conversations, one entry each. |
| `records/tracker.csv` | Your list of actions, one row each. Opens in Excel. |
| `notes/` | Where you drop your own files: meeting notes, transcripts, and the Word document and sheet export for importing. Claude reads from here and never changes anything in it. |
| `.claude/skills/` | Four folders (log, chase, weekly-review, import), each holding a `SKILL.md` file with Claude's step-by-step instructions. |
| `automation.md` | How to have the Monday review drafted for you automatically, and how to have chase messages drafted into Outlook or Slack. |
| `CHANGELOG.md` | What has changed in this template. |
| `LICENSE` | The legal terms for reusing this template. You can ignore it. |
| `.gitignore` | A hidden file that stops git from picking up anything in `notes/`. You can ignore it. |

The `.claude` folder and `.gitignore` start with a dot, so your computer may hide them. On Windows, in File Explorer choose View → Show → Hidden items. On a Mac, in Finder press Command + Shift + full stop.

---

## Before you start: your records are private

Once you start using this, the files in `records/` and `notes/` will hold notes about your staff. Keep them on your work laptop, or wherever your company says staff notes belong. Do not upload your copy to GitHub or any other public site.

---

## Setup

Claude Code runs on your laptop and works directly on the files in this folder, so your records update themselves when you approve a change.

You will need Claude Code on your laptop and switched on for your Enterprise account. If you don't have it, ask your IT team or Claude admin.

1. **Get the files.** Go to https://github.com/tobysambles01/conversation-tracker, click the green **Code** button, then **Download ZIP**. In your Downloads folder, right-click the ZIP and choose **Extract All**, and extract it into your Documents folder. You get a folder called `conversation-tracker-main`; rename it to `conversation-tracker` if you like. Use the ZIP even if you know git: your copy must never be connected to git (see "Updating the template").
2. **Open Claude Code in the folder.** In the Claude desktop app, open the **Code** tab and choose the folder you just extracted. The first time, sign in with your work account. Near where you type there is a model menu: pick the most capable model your company gives you. (If you use Claude Code in a terminal instead, go to the folder and type `claude`.)
3. **Fill in your settings.** Type: `Help me fill in the settings in CLAUDE.md`. Claude asks for your name, your team's names, your preferred spelling and your sign-off, then writes them in. (You can also open `CLAUDE.md` in any text editor and fill in the square brackets yourself.)
4. **Import your history** if you have some. See "Importing your history" below.

From then on you use four commands. Type them where you talk to Claude:

| Type | To |
|---|---|
| `/log` | Log a meeting or conversation. Paste your notes or transcript after it, or give the name of a file you dropped in `notes/`. |
| `/chase` | Draft chase messages for everyone with open actions. Add a name to chase one person: `/chase Jordan`. |
| `/weekly-review` | Draft the Monday review for last week. |
| `/import` | Bring in your old Word document and Google Sheet. |

If you can't use Claude Code, `project-setup.md` explains the fallback, a claude.ai Project; it needs more manual steps and is less tested.

---

## Your daily routine

**After each meeting or conversation**, type `/log` and paste your notes or the transcript. Rough notes are fine. If the notes or transcript are in a file (Teams gives you a `.docx` or `.vtt` file), save it into the `notes/` folder with the date first in its name, such as `2026-11-05-jordan-one-to-one.docx`, and type `/log` followed by the file name.

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
- what **slipped this week** (the deadline moved or passed during the week);
- what is **running late** (it slipped in an earlier week and is still not done);
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

1. **Get your Word document ready.** It should be a .docx file. If it's another format, open it in Word and use File → Save a Copy → Word Document (.docx). Put a copy in the `notes/` folder.
2. **Export your Google Sheet.** In Google Sheets: File → Download → Comma-separated values (.csv). If you use more than one tab, download each one you need. Put them in `notes/` too.
3. **Type `/import`.** Claude asks you three things:
   - the name of the Word document in `notes/`;
   - the name of the sheet export;
   - whether to keep actions you dropped or cancelled. Keeping them, marked "dropped", gives you the complete history.
4. **Check the survey.** Before writing anything, Claude shows what it found: how many meetings and actions, how your columns and status words map across, and the names it found, with suggestions for merging variations ("Jordan", "Jordan E.", "JE"). Correct anything that's wrong.
5. **Approve each batch.** Claude imports a few months at a time, oldest first. For each batch it shows a summary and lists anything it's unsure of, such as possible duplicates or actions with no clear owner. Answer what you can and say "yes" to save. Anything you leave unanswered is marked `[check]`, so you can come back to it by asking "show me everything marked check".

Your original Word document and sheet are never changed, moved or deleted. Keep them as a backup.

A long history can take a while. If you stop part way, type `/import` again later and Claude offers to carry on from where it stopped.

---

## Updating the template

From time to time this template gets improvements (see `CHANGELOG.md`). Your records and notes are yours and are never part of an update.

Your copy must never be connected to git or GitHub. Git can be told to skip `notes/`, but not `records/`, because the blank templates ship in that folder. The ZIP download has no git connection, which is why it is the way to get and update the files.

1. **Keep your settings.** In your `conversation-tracker` folder, rename `CLAUDE.md` to `CLAUDE-old.md`.
2. **Download the new ZIP** the same way as in setup and extract it somewhere else, such as your Downloads folder.
3. **Copy everything across except `records/` and `notes/`.** Open the new folder, select everything in it apart from those two folders, and copy it into your `conversation-tracker` folder. When Windows asks, choose **Replace the files in the destination**. Remember the `.claude` folder is hidden unless you have turned on hidden items. Never copy a new `records/` or `notes/` over yours.
4. **Put your settings back.** Open Claude Code in the folder (a new session) and type: `Copy my settings from CLAUDE-old.md into CLAUDE.md`. Check the top of `CLAUDE.md`, then delete `CLAUDE-old.md` yourself if you like.
5. **Check the records.** Type `/weekly-review`. If the new template added a column to the tracker, Claude adds it to yours and tells you.

---

## Good to know

- **Nothing is ever sent.** Claude only drafts. You send.
- **You approve every change** to your records before it is saved.
- **Nothing is deleted.** Finished actions are marked `done` or `dropped`, with the date they were closed, and stay in the tracker as history.
- **Opening the tracker in Excel:** viewing is fine. If you save it from Excel, Excel may change the dates to its own format. Save it as CSV and check that dates still read like 2026-11-07, or ask Claude to make the change instead.
- **The examples:** the entries C-0000 and A-0000 are invented examples. Claude ignores them. Delete them whenever you like.
- **Spelling:** this guide uses British English. To have Claude write your drafts in US spelling, change "Spelling for drafts" in the settings at the top of `CLAUDE.md` to "US English" (and, in a Project, paste the updated instructions in again).
- **Changing the instructions:** Claude Code reads `CLAUDE.md` and the skill files when a session starts. If you edit them yourself, close Claude Code and open it again (or start a new session in the desktop app) before relying on the change.
- **Backups:** keep a copy of the `records` and `notes` folders somewhere your company approves, such as your work OneDrive.
- **If something goes wrong:** if a command such as `/log` is not recognised, start a new session. If Claude seems to have lost track, start a new session; everything it knows is in the files. If the tracker won't open or looks broken, ask Claude to "check tracker.csv has eleven columns on every row and fix it", and approve the fix. To start again from clean, move the whole folder somewhere else (don't delete it), extract a fresh copy of the ZIP, and copy your `records/` and `notes/` folders into it.
- **Automation:** `automation.md` explains how to have the Monday review drafted automatically and how to have chase messages drafted into Outlook or Slack. Nothing in it is switched on unless you set it up.
