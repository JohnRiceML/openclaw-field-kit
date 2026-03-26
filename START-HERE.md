# You hit your token limit. Here's what to do.

You're here because your AI agents used up their budget too fast. That's a common problem and it's fixable. This guide will walk you through it.

**You don't need to understand why it happened.** You just need to follow the steps below and the AI will handle the rest.

---

## Step 1: Wait for your tokens to reset

Your current session resets on a rolling 5-hour window. You can check how much time is left:

- **On your Mac:** Open the Claude app → click your profile icon (bottom left) → you'll see your usage bar and when it resets.

Once it resets, move to Step 2. Don't skip ahead — you'll just hit the limit again.

---

## Step 2: Pick where to type

You probably have one or more of these available. **Pick whichever one you're most comfortable with.** They all work.

### Option A: Claude Desktop (the app on your Mac)

1. Open the **Claude** app on your Mac
2. Start a **new conversation** (click the + button or hit Cmd+N)
3. Go to Step 3

### Option B: OpenClaw (if you have it running)

1. Open a chat with **any of your agents**
2. Start a fresh session by typing `/new`
3. Go to Step 3

### Option C: Claude Code (the terminal tool)

1. Open your **Terminal** app (search "Terminal" in Spotlight)
2. Type `claude` and press Enter
3. Go to Step 3

### Option D: Discord or Telegram (if your agent is connected there)

1. Open **Discord** or **Telegram**
2. Go to the chat with your agent
3. Type `/new` to start a fresh session
4. Go to Step 3

---

## Step 3: Install the tools that fix this

Copy and paste this entire message into the chat from Step 2:

> I need help fixing my token usage. Please run these two commands for me:
>
> First: `git clone https://github.com/JohnRiceML/openclaw-field-kit.git ~/openclaw-field-kit`
>
> Then: `cp -r ~/openclaw-field-kit/skills/* ~/.openclaw/skills/`
>
> After that, tell me it's done.

Wait for it to confirm the install is complete.

**If that doesn't work** (maybe you don't have OpenClaw yet, or something errors), skip to [Plan B](#plan-b-no-install-needed) at the bottom of this page.

---

## Step 4: Run the Context Doctor

Now type this in the same chat:

```
/context-doctor
```

The Context Doctor will:
1. Check what's using up your token budget
2. Explain what it finds in plain English
3. Walk you through the fixes, one at a time
4. Ask your permission before changing anything

**Just follow along and answer its questions.** It's designed to be a conversation — you don't need to know the technical details.

---

## Step 5: There is no Step 5

The Context Doctor handles it from here. When it's done, it'll give you a summary of what changed and what to expect going forward.

If you want to set up automated tasks later, you can type `/cron-builder`. If something breaks, type `/troubleshooter`. These are all part of the same toolkit.

---

## Plan B: No install needed

If the install in Step 3 didn't work, you can still get help without installing anything.

1. Go to this page: **[Context Doctor skill file](https://github.com/JohnRiceML/openclaw-field-kit/blob/main/skills/context-doctor/SKILL.md)**
2. Click the **"Raw"** button (top right of the file)
3. Select all the text (Cmd+A) and copy it (Cmd+C)
4. Go back to your chat from Step 2
5. Paste it in (Cmd+V)
6. On the next line, type: **"I hit my token limit this morning. Can you help me figure out why and fix it?"**
7. Press Enter

The AI will read those instructions and walk you through the same process.

---

## What probably happened

*(You don't need to read this — it's just context if you're curious.)*

Every time you send a message to an AI agent, it costs "tokens." Think of tokens like fuel. Some things burn more fuel than others:

- **More powerful models burn fuel faster.** Opus (the most powerful) uses about 1.7x more than Sonnet. Like putting premium gas in when regular works fine for most driving.
- **Building new agents is expensive.** Each new agent loads a full set of instructions from scratch — no shortcuts the first time.
- **Long conversations add up.** Every message you've sent in a session gets re-read by the AI on every turn. The longer the conversation, the more fuel per message.
- **Detailed responses cost more.** Compliance topics generate long, thorough answers — those response tokens cost 5x what input tokens cost.

The Context Doctor helps you fix all of these without needing to understand the details.
