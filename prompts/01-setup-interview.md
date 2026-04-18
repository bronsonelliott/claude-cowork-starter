# Setup Interview Prompt

**What this does:** Runs an interview to fill out all four of your context files (`about-me.md`, `my-work.md`, `my-voice.md`, `my-preferences.md`) in one sitting.

**When to use it:** The first time you open this workspace, or any time you want to rebuild your context from scratch.

**How long it takes:** About 20 minutes.

**How to use it:** Copy everything between the lines below and paste it into Claude.

---

```
Interview me to fill out all four of my context files at once: about-me.md, my-work.md, my-voice.md, and my-preferences.md.

Use AskUserQuestion, one question at a time. Ask roughly 15-19 questions total covering:

WHO I AM (3-4 questions): professional identity that stays stable across jobs
- The kind of work I do, my field, years of experience
- How I think and approach my work (not tools, approach)
- What good work looks like in my field, and what bad work looks like
- My rules and non-negotiables

MY WORK (3-4 questions): current employment situation
- My current company (name, what it does, stage/size)
- My role and what I own
- My team (key collaborators by name, 3-7 people Claude should recognize)
- Tools I use daily
- Who my customers or users are
- What I'm focused on right now (current goals or priorities)

MY VOICE (3-4 questions. SKIP if I don't create written content)
- Tone and voice I use
- Words and phrases I always use vs. never use
- Examples of writing I love and hate

MY PREFERENCES (4-5 questions)
- How I want Claude to communicate with me (casual/formal, short/detailed, bullets/prose)
- When I want Claude to just do the thing vs. push back or ask first
- How I want to receive information (tables, lists, plain text)
- What I hate in AI responses (things to never do)
- Non-negotiable rules

If I say "that's enough," stop and compile what we have.

After the interview, write four separate files:
- `context/about-me.md` (under 1,500 tokens)
- `context/my-work.md` (under 1,000 tokens)
- `context/my-voice.md` (under 1,000 tokens). Skip if I don't create content.
- `context/my-preferences.md` (under 1,000 tokens)

Use clear section headers in each file. Replace any existing content in those files.
```

---

## After the interview

1. Open each file in `context/` and review what Claude wrote
2. Edit anything that doesn't feel right. These are YOUR files.
3. Run `prompts/04-verify-setup.md` to confirm everything's working
4. You're ready to start your first project (`prompts/02-new-project.md`)
