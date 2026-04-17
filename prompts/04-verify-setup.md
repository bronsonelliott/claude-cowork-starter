# Verify Setup Prompt

**What this does:** Asks Claude to confirm your workspace is configured correctly and that your context files are loading.

**When to use it:**
- Right after you finish the setup interview
- After making changes to context files
- Whenever Claude seems to have "forgotten" who you are
- Periodically as a sanity check

**How long it takes:** Under 1 minute.

**How to use it:** Copy everything between the lines below and paste it into Claude.

---

```
Run a setup verification on my Cowork workspace. Check the following and report back:

1. Did you read CLAUDE.md at the workspace level? Confirm what folder I'm in.

2. Did you read the files in `context/`? Tell me what you learned about:
   - Who I am (from about-me.md)
   - My voice (from my-voice.md, if filled in)
   - My preferences (from my-preferences.md)

3. List any context files that appear empty or contain only the original placeholder/stub content.

4. List the projects (if any) you can see in `projects/`.

5. Flag any obvious problems — missing files, contradictions in my context, or anything that looks misconfigured.

Be honest. If something isn't working, tell me clearly so I can fix it.
```

---

## What a healthy response looks like

- Claude knows the folder you're in
- Claude can summarize specific facts from your context files (your role, communication style, etc.)
- No empty or stub-only context files (unless you intentionally skipped one — like `my-voice.md` if you don't create content)
- No flagged problems

## If verification reveals problems

| Problem | Fix |
|---|---|
| "I don't see any context files" | You may have launched Cowork from a project subfolder. Close and reopen, selecting your workspace folder. |
| "Context files appear empty" | Run `prompts/01-setup-interview.md` to fill them out, or edit the files manually. |
| "I can't tell what folder I'm in" | Confirm CLAUDE.md exists at the workspace level — it should have been created when you set up the starter. |
| Generic answers about you | The context files exist but Claude isn't loading them. Check that CLAUDE.md still has the "read all files in `context/`" instruction. |
