# OpenClaw Field Kit

Practical skills and guides for non-technical teams running OpenClaw. Born from real problems we hit helping organizations get set up.

## What's in the kit

| Skill | Command | What it does |
|-------|---------|-------------|
| [setup-guide](skills/setup-guide/) | `/setup-guide` | Step-by-step OpenClaw installation for first-timers |
| [context-doctor](skills/context-doctor/) | `/context-doctor` | Diagnose and fix token usage, context bloat, and session limits |
| [troubleshooter](skills/troubleshooter/) | `/troubleshooter` | Hit a wall? This reads the docs and walks you through the fix |
| [cron-builder](skills/cron-builder/) | `/cron-builder` | Set up resilient cron jobs with vertical agents and self-healing monitoring |

## How to use

### If you already have OpenClaw running

Copy any skill folder into your skills directory:

```bash
# Available globally
cp -r skills/context-doctor ~/.openclaw/skills/context-doctor

# Or in a specific workspace
cp -r skills/context-doctor <your-workspace>/skills/context-doctor
```

Then type the slash command in any agent chat (e.g. `/context-doctor`).

### If you're just getting started

Open Claude Desktop or Claude Code, paste the contents of [setup-guide/SKILL.md](skills/setup-guide/SKILL.md) into the chat, and say:

> "Follow these instructions to help me install OpenClaw on my computer."

Claude will read the official docs, check your system, and walk you through everything step by step.

### If something breaks

Same idea — open Claude Desktop or Claude Code, paste [troubleshooter/SKILL.md](skills/troubleshooter/SKILL.md), and describe what's going wrong. It'll read the relevant OpenClaw docs and help you fix it.

## Who this is for

You don't need to be technical to use these. Each skill is designed to walk you through things step by step, explain tradeoffs in plain language, and never make changes without asking first.

## Contributing

Got a problem you keep running into when helping orgs set up OpenClaw? Turn it into a skill.

1. Create a new folder under `skills/` with your skill name
2. Add a `SKILL.md` following the [OpenClaw skill format](https://docs.openclaw.ai/skills)
3. Write it for someone who is NOT an engineer — plain language, analogies, one concept at a time
4. Open a PR

### Guidelines

- **No jargon without an explanation.** If you have to use a technical term, define it with an analogy first.
- **Always ask before changing anything.** These skills guide — they don't auto-pilot.
- **Explain tradeoffs.** Every optimization has a cost. Be honest about it.
- **Keep it short.** One idea at a time. Check understanding before moving on.

## License

MIT
