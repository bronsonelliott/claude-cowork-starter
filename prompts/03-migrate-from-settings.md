# Migration Prompt (From Settings to Workspace)

**What this does:** Takes content from your existing Claude Personal Preferences or Cowork Global Instructions and splits it across the right context files in this workspace.

**When to use it:** If you already have content in Settings → Personal Preferences (or Cowork Global Instructions) and want to migrate it INTO this workspace instead of duplicating it.

**Why migrate:** Keeping the same info in both Settings AND workspace files doubles your context load and creates headaches when things change. Pick one source of truth — and this guide recommends the workspace.

**How long it takes:** About 5 minutes.

---

## Before you start

1. Open Claude's Settings → Personal Preferences
2. Copy ALL the content there into a temporary document as a safety net
3. Also check Cowork Settings → Global Instructions and copy that content if there's any

Don't clear Settings yet — wait until you've reviewed the migration results.

---

## The prompt

Copy everything between the lines below. Then REPLACE the `[PASTE YOUR EXISTING PREFERENCES HERE]` section with your actual Settings content. Paste the whole thing into Claude.

---

```
I'm migrating my existing Claude preferences into my workspace context files. Below is the content currently in my Personal Preferences and/or Cowork Global Instructions. Please:

1. Read through it carefully
2. Split the content across my three context files based on what each section is about:
   - `context/about-me.md` → who I am, role, background, how I think, my situation
   - `context/my-voice.md` → how I write or speak, tone, words I use or avoid (skip if not applicable)
   - `context/my-preferences.md` → how I want you to communicate with me, formatting, working style, rules, error handling
3. Write each file to its location in `context/` — REPLACE any existing content in those files
4. Show me a summary of what content went into each file
5. Flag anything that didn't clearly fit in one of the three — I'll decide where it goes

After you're done, I'll review the files. If they look good, I'll clear my Settings to avoid duplicate context.

Here's my existing content:
---
[PASTE YOUR EXISTING PREFERENCES HERE]
---
```

---

## After migration

1. Open each file in `context/` and review what Claude wrote
2. Edit anything that doesn't feel right
3. If the files look good: clear Personal Preferences and Cowork Global Instructions in Settings
4. Keep your temporary backup document for a week in case you want to recover
5. Test with a fresh Cowork session — ask Claude "what do you know about me?" to confirm nothing got lost

## Safety net rule

Don't clear your Settings until you've tested that the workspace context files are working. If something feels off after the migration, you can restore from your backup document.
