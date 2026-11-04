# Automation (optional)

This page describes two things you can set up later if you want them:

1. having the Monday review drafted for you at 8am every Monday;
2. having chase messages and the review drafted straight into Outlook or Slack.

**Nothing on this page is switched on.** The template works without any of it. Whatever you set up, the rule stays the same: Claude drafts, you send.

Menu names in Claude's apps change from time to time, so the steps below describe what to look for rather than every click.

---

## 1. The Monday 8am review

### If you use Claude Code (through the Claude desktop app)

The Claude desktop app can run a task on a schedule on your own laptop. Because it runs on your laptop, it reads your records where they are and they never leave your machine.

1. Open the Claude desktop app and find **Scheduled tasks** (or similar).
2. Create a new task:
   - **Folder:** your `conversation-tracker` folder.
   - **When:** weekly, Monday, 08:00.
   - **Instructions:** paste this:

     > Run /weekly-review for last week, Monday to Sunday. Leave the review as a draft in this session for me to read. Do not send or post it anywhere and do not change any files.

3. Save the task.

On Monday morning, open the app and you will find the review waiting in that task's session. Read it, edit it if you like, and paste it into your email or Slack.

Things to know:

- Your laptop needs to be switched on, and the Claude app running, at the time. Check in the app what happens to a run that is missed while the laptop is asleep or off.
- The weekly review only reads the records, so it is safe to run while you are away. Don't schedule `/log` or `/import`: they need your answers and approval.
- Claude Code also offers scheduled tasks that run in the cloud ("routines"). These work from a copy of the folder held on GitHub. **Don't use them for this.** Your records hold staff information and must not go to GitHub.

### If you use a claude.ai Project

Projects can't run on a schedule. Instead, put a recurring reminder in your Outlook calendar for 8am on Mondays that says "Open the Conversation tracker project and type: weekly review". It takes under a minute.

---

## 2. Drafting into Outlook or Slack with connectors

Connectors let Claude work with other tools, such as Outlook and Slack. With the right connector, Claude can put each chase message into Outlook as a **draft email**, addressed and ready, so all you do is check it and press Send.

### What you need

- **Your Claude admin** to make the connector available to your organisation (for example the Microsoft 365 connector for Outlook, or the Slack connector).
- **You** to connect your own account to it, in Claude under Settings → Connectors. The same connectors are available to Claude Code when you use it through the Claude desktop app.

### How you use it

After `/chase` has drafted the messages, say for example:

> Put these into Outlook as draft emails, one per person. Don't send them.

Claude creates one draft per person in your Outlook Drafts folder and tells you which ones it made. If it can't find someone's email address, it asks you.

The same works for the review:

> Put this week's review into an Outlook draft to the team. Don't send it.

### Slack

Check what the Slack connector your company uses can do. Some can save a draft message; some can only send. If it can only send, don't use it for this: copy the message from Claude and paste it into Slack yourself. The instructions in `CLAUDE.md` already tell Claude to stop rather than send.

### Belt and braces: block the send buttons

The instructions in `CLAUDE.md` tell Claude never to send. You can make that a hard rule as well:

- **In claude.ai:** in the connector's settings, if it lists its individual tools, set every tool that sends (send email, send message, post message, reply, forward) to "never allow", and leave the tools that create drafts on "ask" or "allow".
- **In Claude Code:** ask Claude to "list the tools this connector provides and add every tool that sends something to the deny list in this folder's local Claude Code settings". Claude shows you the change before making it. Once denied, those tools can't be used from this folder, even by mistake.

Your admin may also be able to switch off sending tools for the whole organisation.
