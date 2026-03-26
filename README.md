# OpenClaw Field Kit

**Drop-in skills that help non-technical people set up, run, and fix [OpenClaw](https://openclaw.ai) — without needing to read the docs themselves.**

Born from real problems we kept hitting while helping organizations get their agents running. Every skill in this kit was built because someone got stuck and we turned the fix into a reusable guide.

---

## What's the idea?

OpenClaw is powerful, but the docs are written for engineers. If you're a founder, operator, or team lead trying to get AI agents working for your organization, you shouldn't need to understand context windows or cron syntax to get value out of it.

These skills act as **interactive assistants** — you type a slash command, and an AI guide walks you through the process step by step, in plain language, asking before it changes anything.

---

## What's in the kit

| Skill | Command | What it does |
|-------|---------|-------------|
| [Setup Guide](skills/setup-guide/) | `/setup-guide` | Walks you through installing OpenClaw from scratch |
| [Context Doctor](skills/context-doctor/) | `/context-doctor` | Diagnoses why you're burning through tokens and fixes it |
| [Troubleshooter](skills/troubleshooter/) | `/troubleshooter` | When something breaks, reads the docs for you and walks you through the fix |
| [Cron Builder](skills/cron-builder/) | `/cron-builder` | Sets up automated jobs with focused agents and self-healing monitoring |

### Setup Guide

Your starting point. Opens in Claude Desktop or Claude Code and walks you through the full OpenClaw installation — checking your system, running the installer, verifying the gateway, and sending your first message. Explains every step before running it.

### Context Doctor

For when you hit your session limit or things feel slow. Runs diagnostics on your context window, shows you exactly what's eating your tokens, and walks you through the fixes — compaction, caching, trimming system prompts, model routing. Explains every tradeoff so you can decide what makes sense.

### Troubleshooter

The "it's broken and I don't know why" skill. You describe the problem in your own words, it reads the relevant OpenClaw documentation, figures out what's wrong, and walks you through the fix. If it can't solve it, it summarizes what it tried so you can get help from the community.

### Cron Builder

For automating recurring work — daily summaries, inbox monitoring, weekly reports. Built around three principles:

1. **Vertical agents** — one small, focused agent per job instead of one mega-agent that does everything. When something breaks, you know exactly which piece broke.
2. **Test before you ship** — every job gets tested manually before it goes live. No exceptions.
3. **Self-healing monitoring** — builds a watchdog agent that checks your other agents, re-runs failed jobs, and alerts you when something needs attention.

---

## How to use these

### Option 1: You already have OpenClaw running

**Install a single skill:**

```bash
# Clone the repo
git clone https://github.com/JohnRiceML/openclaw-field-kit.git

# Copy the skill you want into your OpenClaw skills folder
cp -r openclaw-field-kit/skills/context-doctor ~/.openclaw/skills/context-doctor
```

**Install all skills at once:**

```bash
git clone https://github.com/JohnRiceML/openclaw-field-kit.git
cp -r openclaw-field-kit/skills/* ~/.openclaw/skills/
```

Then type the slash command in any agent chat:

```
/context-doctor
/troubleshooter
/cron-builder
```

The skill loads and the agent switches into guide mode, walking you through everything interactively.

### Option 2: You don't have OpenClaw yet

No problem — that's what the setup guide is for.

1. Open **Claude Desktop** (the app) or **Claude Code** (the terminal tool)
2. Go to the [setup-guide SKILL.md](skills/setup-guide/SKILL.md) file in this repo
3. Copy its contents and paste it into the chat
4. Say: **"Follow these instructions to help me install OpenClaw on my computer."**

Claude will check your system, install OpenClaw, and walk you through the whole process. Once OpenClaw is running, you can install the rest of the skills normally.

### Option 3: You just need help with one thing right now

You don't need to install anything. Open Claude Desktop or Claude Code, copy the contents of whichever skill file you need, paste it into the chat, and describe your problem. The skill instructions tell Claude how to help you.

---

## How these skills work

Each skill is a single Markdown file (`SKILL.md`) that gives the AI a specific role and a structured walkthrough process. When you run the slash command, OpenClaw loads the instructions and the agent becomes that specialist.

Every skill follows the same principles:

- **No jargon without an explanation.** Technical terms get a plain-English analogy first.
- **Never changes anything without asking.** You're always in control.
- **Explains tradeoffs honestly.** Every optimization has a cost — the skill tells you what it is so you can decide.
- **One step at a time.** Checks that you understand before moving on.

---

## Common scenarios

**"I just got access to OpenClaw and have no idea where to start."**
> Use `/setup-guide`. It handles everything from installation to your first message.

**"My agent hit its token limit halfway through the morning."**
> Use `/context-doctor`. It'll show you what's eating your tokens and help you fix it — usually prompt caching and compaction get you back on track fast.

**"I got an error and I don't understand what it means."**
> Use `/troubleshooter`. Describe what happened in your own words. It reads the OpenClaw docs, figures out the fix, and walks you through it.

**"I keep doing the same thing manually every day and want to automate it."**
> Use `/cron-builder`. It'll help you set up a focused agent, test it, schedule it, and build monitoring so you know if it ever breaks.

**"I set up a bunch of agents and now everything is slow and expensive."**
> Start with `/context-doctor` to trim the fat, then `/cron-builder` if you want to restructure your agents into smaller, focused pieces.

---

## Contributing

We add new skills when we hit a problem enough times that it deserves a reusable fix. If you're helping people set up OpenClaw and keep running into the same issue, turn it into a skill.

### How to add a skill

1. Create a folder under `skills/` with a descriptive name (e.g., `skills/my-new-skill/`)
2. Add a `SKILL.md` file with [OpenClaw skill frontmatter](https://docs.openclaw.ai/skills):

```markdown
---
name: my-new-skill
description: One line explaining what it does.
user-invocable: true
---

# Skill Name

Instructions for the AI go here...
```

3. Open a PR with a short description of the problem this skill solves

### Guidelines for writing skills

- **Write for someone who is not an engineer.** If your mom or your sales lead couldn't follow it, simplify it.
- **Always ask before changing anything.** Guide, don't auto-pilot.
- **Explain tradeoffs.** Don't just say "do this" — say "this saves tokens but you might lose some detail from older messages."
- **Include a test step.** If the skill sets something up, it should verify that it worked before moving on.
- **Keep SKILL.md focused.** One skill, one problem. If it's doing too many things, split it up.
- **Link to the official docs.** Skills should reference [docs.openclaw.ai](https://docs.openclaw.ai) so the AI can fetch current information rather than relying on stale instructions.

---

## License

MIT
