# OpenClaw Field Kit

**You don't need to be technical to run AI agents.** This kit gives you interactive guides that walk you through everything — step by step, in plain English, and they always ask before changing anything.

> *"Think of these as having a friendly expert sitting next to you while you set things up."*

**Hit your token limit?** Go straight to **[START-HERE.md](START-HERE.md)** — it tells you exactly what to open, what to type, and where to type it.

---

## What problem does this solve?

[OpenClaw](https://openclaw.ai) lets you run AI agents on your own computer. It's powerful — but the documentation assumes you're a software engineer.

If you're a **founder, operator, team lead, or anyone who isn't an engineer**, this kit bridges that gap. Instead of reading docs, you type a simple command and an AI guide walks you through it like a conversation.

---

## What's inside

### `/setup-guide` — Get OpenClaw running on your computer

For your first day. Checks your computer, installs everything, and walks you through sending your first message. You don't need to know what a "gateway" or "terminal" is — it explains as it goes.

**Use this when:** You just heard about OpenClaw and want to try it.

---

### `/context-doctor` — Fix slow or expensive agents

Your agents have a "memory budget" for each conversation. When it fills up, things get slow or stop working. This guide checks what's using up that budget and helps you free up space.

**Use this when:**
- You hit a message that says you're out of tokens or at your session limit
- Your agents feel slow or expensive
- You upgraded to a more powerful model and burned through your limit faster than expected

---

### `/troubleshooter` — Fix anything that breaks

Describe your problem in your own words. This guide goes and reads the official OpenClaw documentation *for you*, figures out what's wrong, and walks you through the fix. No Googling required.

**Use this when:**
- You see an error message you don't understand
- Something that was working yesterday stopped working today
- You're stuck and don't know what to do next

---

### `/cron-builder` — Automate tasks that you keep doing manually

Sets up scheduled jobs — like a daily summary, inbox check, or weekly report — that run automatically. Built around a simple idea: **small, focused agents that each do one thing well**, with a watchdog agent that makes sure everything keeps running.

**Use this when:**
- You keep doing the same thing every day and wish it just happened on its own
- You want daily briefings, automated reports, or regular monitoring
- You tried to automate something and it broke — this rebuilds it the right way

---

## Getting started

### "I don't have OpenClaw yet."

You'll need [Claude Desktop](https://claude.ai) (the app) or [Claude Code](https://claude.ai) (the terminal version) — you probably already have one of these.

1. Open Claude
2. Click on the [Setup Guide skill file](skills/setup-guide/SKILL.md) in this repo
3. Copy everything in the file
4. Paste it into your Claude chat
5. Type: **"Help me install OpenClaw"**

That's it. Claude takes it from there — checks your system, installs OpenClaw, and gets you up and running.

### "I already have OpenClaw running."

**Easiest way — install everything at once:**

Ask your agent (or Claude) to run these two commands for you:

```
git clone https://github.com/JohnRiceML/openclaw-field-kit.git ~/openclaw-field-kit
cp -r ~/openclaw-field-kit/skills/* ~/.openclaw/skills/
```

Or just tell your agent:

> *"Go to github.com/JohnRiceML/openclaw-field-kit, download the skills, and install them into my OpenClaw skills folder."*

It'll figure it out.

**Then use any skill by typing its command:**

```
/setup-guide
/context-doctor
/troubleshooter
/cron-builder
```

Your agent switches into guide mode and walks you through everything.

### "I just need help with one thing right now."

You don't need to install anything.

1. Click on the skill file you need (links above)
2. Copy the contents
3. Paste it into any Claude or OpenClaw chat
4. Describe your problem

The instructions tell the AI exactly how to help you.

---

## How it works (the short version)

Each skill is a file that tells the AI: *"Here's who you are right now, here's the process to follow, and here are the rules — go slow, explain everything, and don't touch anything without asking."*

When you run the command, your agent reads that file and becomes that specialist. It's like calling in an expert for a specific job.

**Every skill in this kit follows these rules:**

- Explains things in everyday language — no jargon without an analogy first
- Never makes changes without your permission
- Goes one step at a time and checks that you're following
- Tells you the tradeoffs honestly so you can make the call
- If it doesn't know something, it says so instead of guessing

---

## Quick answers

**"What if I mess something up?"**
> These skills are designed to be safe. They always ask before changing anything, and most changes are reversible. If something does go wrong, use `/troubleshooter` to fix it.

**"Do I need to be technical to use these?"**
> No. That's the whole point. If you can have a conversation, you can use these.

**"Do I need to install all of them?"**
> No. Grab whichever ones you need. They work independently.

**"Can I use these with Claude Desktop instead of OpenClaw?"**
> Yes! Just copy the contents of any skill file, paste it into Claude Desktop, and describe what you need help with. The slash commands only work inside OpenClaw, but the skill instructions work anywhere Claude runs.

**"My agent maxed out its session this morning. Which skill do I need?"**
> `/context-doctor`. It'll figure out what's eating your budget and help you fix it. Usually takes a few minutes.

**"I want to automate something but I'm nervous about things running on autopilot."**
> `/cron-builder` tests everything manually before scheduling it. Nothing runs on autopilot until you've seen it work and said "yes, turn it on." It also builds a watchdog that alerts you if anything breaks.

---

## Built by people who keep helping people set up OpenClaw

Every skill in this kit exists because someone got stuck and we turned the solution into a reusable guide. If you're helping others get set up and keep running into the same problem, we'd love your contribution.

**To add a new skill:** Create a folder in `skills/`, add a `SKILL.md` file following the [OpenClaw skill format](https://docs.openclaw.ai/skills), and open a pull request. The only rule: **write it for someone who is not an engineer.**

See the [contributing guide](CONTRIBUTING.md) for details.

---

## License

MIT — use it however you want.
