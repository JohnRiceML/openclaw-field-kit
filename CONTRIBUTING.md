# Contributing to the Field Kit

Thanks for helping make OpenClaw easier for non-technical people. Here's how to add a new skill.

## When to create a skill

If you keep running into the same problem while helping people set up OpenClaw, that's a skill waiting to be written. The bar is simple: **did this come up more than once?**

## How to create a skill

### 1. Create a folder

```
skills/your-skill-name/SKILL.md
```

Pick a name that describes what it does, not how it works. Good: `context-doctor`, `setup-guide`. Not great: `token-optimization-v2`, `config-editor`.

### 2. Write the SKILL.md

Start with the frontmatter:

```markdown
---
name: your-skill-name
description: One sentence a non-technical person would understand.
user-invocable: true
---
```

Then write the instructions. This is the hard part — you're writing for two audiences:
- **The AI** that will follow these instructions
- **The non-technical person** who will experience the result

### 3. Open a pull request

Describe the problem this skill solves and who it's for. That's it.

## The golden rule

**Write for someone who is not an engineer.**

Before you submit, read your skill and ask: *"Would my sales lead be able to follow this?"* If not, simplify.

## Writing guidelines

### Language
- No jargon without an analogy. "Context window" becomes "think of it like a backpack — it can only hold so much."
- Short sentences. One idea at a time.
- Use "you" and "your", not "the user" or "one should."

### Behavior
- Always ask before changing anything. The skill guides — it doesn't auto-pilot.
- Explain tradeoffs. Don't just say "do this." Say "this saves money but your agent might forget some older details."
- Include a test/verification step. If you set something up, prove it worked before moving on.

### Structure
- Start with a friendly intro that sets expectations
- Walk through the process in clear numbered steps
- End with a summary of what was done and what to do next
- Include a quick reference section for commands and settings

### Scope
- One skill, one problem. If it's doing three things, split it into three skills.
- Link to [docs.openclaw.ai](https://docs.openclaw.ai) so the AI can fetch current info rather than relying on what was true when the skill was written.
- Reference other skills in the kit when relevant (e.g., "if this turns out to be a token issue, try `/context-doctor`").

## Questions?

Open an issue. There are no dumb questions — that's kind of the whole point of this project.
