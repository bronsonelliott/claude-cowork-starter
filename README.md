# Setting Up Claude Cowork: A Step-by-Step Guide

A no-install, no-code setup for your Claude Cowork workspace. Works for total beginners, scales up to power users, and stays compatible with Claude Code if you ever switch tools.

---

## What this is

A walkthrough for setting up a Claude Cowork workspace from scratch. You'll end up with:

- A dedicated workspace folder on your computer
- Context files that tell Claude who you are, how you work, and what "good" looks like
- A project structure that keeps every project self-contained and portable
- Zero plugins installed, zero command-line work required

Built for anyone — technical or not.

---

## The philosophy in 60 seconds

Claude Cowork automatically reads a file called `CLAUDE.md` when you open a folder. That's the built-in feature — everything else you might have seen online is just different opinions about what to put in that file and what other files to put next to it.

This guide uses five principles:

1. **A CLAUDE.md file at the top of your workspace folder** loads automatically every session — no settings to configure
2. **Context files in a `context/` folder** describe who you are, your voice, and your preferences
3. **Each project is self-contained** — its own folder with its own rules, inputs, and outputs
4. **Settings stay minimal** — everything important lives in the workspace folder so it's portable
5. **Works in Claude Code too** — the same folder structure is recognized by both tools

One folder. One convention. Everything else is flavor.

---

## The five layers of context (good to know)

When Claude opens a conversation, it reads context from up to five places. This guide uses the bottom three:

| Layer | Scope | Portable? | This guide uses it? |
|---|---|---|---|
| 1. Claude Personal Preferences | All Claude products | No | Keep minimal or empty |
| 2. Cowork Global Instructions | All Cowork sessions | No | Keep empty |
| 3. Workspace CLAUDE.md | One workspace folder | Yes | Primary source of truth |
| 4. Project CLAUDE.md | One project subfolder | Yes | Per-project overrides |
| 5. Context files (via CLAUDE.md) | Referenced by workspace CLAUDE.md | Yes | Detailed context about you |

**Rule of thumb:** if it fits in your workspace folder, put it there. Only use settings fields for things that must also apply OUTSIDE Cowork.

---

## Before you start

### You'll need

- A computer (Mac or Windows)
- A Claude account
- The Claude desktop app installed (download from claude.ai/download)
- About 30 minutes

### Check your existing settings (important)

This guide assumes a fresh setup. Before starting, check two places:

1. **Claude Personal Preferences** (Claude desktop app → Settings → Personal Preferences)
2. **Cowork Global Instructions** (Cowork Settings → Global Instructions)

**If both are empty:** proceed to Phase 1.

**If either has content:** see the "Already Have Preferences?" section at the end of this guide before continuing. You'll need to decide whether to migrate that content into the workspace setup, or keep it where it is and skip related interview questions later.

---

## Phase 1: Create your workspace folder

**Step 1 — Pick a location.** Good options: Documents, Desktop, or a synced folder like Dropbox or iCloud. Avoid putting it inside other project folders.

**Step 2 — Create the folder.**

1. Open Finder (Mac) or File Explorer (Windows)
2. Navigate to your chosen location
3. Right-click → New Folder
4. Name it `Cowork-Workspace` (no spaces makes it easier to reference)

Leave the folder empty. Close the window.

---

## Phase 2: Open the folder in Cowork

**Step 3 — Launch the Claude desktop app.** Find the Claude icon and open it.

**Step 4 — Enter Cowork mode.** Look for a "Cowork" button, toggle, or menu option in the Claude interface.

**Step 5 — Select your workspace folder.**

1. When prompted, click "Select Folder" or the folder-picker option
2. Navigate to `Cowork-Workspace`
3. Click "Select" or "Open"

**Check it worked:** type *"what folder am I working in?"* Claude should respond with the path to your Cowork-Workspace folder.

> **Critical habit from day one:** ALWAYS select your `Cowork-Workspace` folder — never a project subfolder inside it. This is the single most important rule. If you accidentally open a subfolder, Claude won't load your global context and will seem to "forget" who you are.

---

## Phase 3: Verify the starter structure

This starter folder already has the structure built for you. Just verify it's all there.

**Step 6 — Open your workspace folder in Finder (Mac) or File Explorer (Windows). You should see:**

```
Cowork-Workspace/
├── START-HERE.md
├── README.md              ← you're reading this
├── CLAUDE.md              ← workspace rules (already configured)
├── context/
│   ├── about-me.md       ← stub, ready to fill out
│   ├── my-voice.md       ← stub, ready to fill out
│   └── my-preferences.md ← stub, ready to fill out
├── prompts/
│   ├── 01-setup-interview.md
│   ├── 02-new-project.md
│   ├── 03-migrate-from-settings.md
│   └── 04-verify-setup.md
└── projects/
    └── README.md          ← explains how project folders work
```

If everything's there, you're ready for Phase 4. If anything's missing, your starter folder didn't unzip correctly — re-download it.

> **If you're building from scratch (no starter folder):** see the appendix at the end of this guide for the prompt to create this structure manually.

---

## Phase 4: Fill out your context files

**Step 7 — Open `prompts/01-setup-interview.md`**, copy the prompt inside it, and paste into Claude.

Claude will interview you for about 15 minutes — covering who you are, your voice (optional), and your preferences — then write the results to your three context files automatically.

**Tip:** if you say "that's enough" at any point, Claude will stop and compile what you've shared so far.

### Alternative: three separate interviews

If you want a deeper, more thorough exploration of each area, see the Appendix at the end of this guide for three separate interview prompts you can run individually.

---

## Phase 5: Test your setup

**Step 8 — Start a fresh Cowork session.** Close your current session and reopen, selecting the same `Cowork-Workspace` folder.

**Step 9 — Verify context is loading.** Open `prompts/04-verify-setup.md`, copy the prompt inside, and paste it into Claude. It will tell you what context loaded successfully and flag any problems.

Or just ask informally: *"What do you know about me based on my workspace context?"* Claude should respond with specifics — your role, preferences, tone. If you get generic answers, see the troubleshooting table at the end of this guide.

---

## Phase 6: Start your first real project

**Step 10 — Open `prompts/02-new-project.md`**, copy the prompt inside, and paste into Claude.

Claude will ask for the project name, create the folder structure (CLAUDE.md, inputs/, outputs/), then ask 5 short questions about project-specific rules and fill in the project CLAUDE.md from your answers. Takes about 2-3 minutes total.

**Where to put files as you work:**

- Research, reference PDFs, source spreadsheets → project's `inputs/` folder
- Drafts and work-in-progress → keep at the top of the project folder
- Finished, ready-to-ship deliverables → project's `outputs/` folder

The whole project stays together. If you need to hand it off or archive it, zip up the project folder and you have everything.

---

## Phase 7: Ongoing habits

Three habits that keep this system working:

1. **Always select your Cowork-Workspace folder when launching Cowork.** Never select a project subfolder. Your Cowork-Workspace folder is where your global context lives — if you start inside a project folder instead, Claude won't see your context files.
2. **Update context files when things change.** New role? New tool? Just tell Claude: *"Update my about-me.md — I'm now doing X."*
3. **Keep context files tight.** If any one file gets over 2,000 words, trim it. Long context files slow down every session.

---

## Advanced setup

### Adding new context files

Drop a new `.md` file into `context/`. Claude picks it up automatically at the next session start — the instruction "read all files in `context/`" handles any number of files. No CLAUDE.md edits required.

Common files users add as they grow:

- `technical-preferences.md` — coding, testing, security, version control rules
- `industry-terms.md` — glossary of jargon specific to your field
- `recurring-people.md` — team members, clients, or stakeholders Claude should know about
- `tools-and-systems.md` — the apps, platforms, and workflows you use daily
- `meeting-rhythms.md` — your standing meetings, recurring agendas, or workflows

### When you DO need to update CLAUDE.md

Only when you want Claude to treat one file differently from the others. For example:

- *"When writing for clients, use `brand-voice.md`. For personal posts, use `my-voice.md`."*
- *"Prioritize rules in `critical-rules.md` over everything else."*
- *"Only load `industry-terms.md` when the conversation involves technical topics."*

Without these explicit instructions, Claude treats all context files as equal weight — which is usually fine.

### Graduating to project-level overrides

When a rule only applies to ONE project, move it out of `context/` and into that project's CLAUDE.md:

```
projects/client-acme/
├── CLAUDE.md          ← "formal tone, APA citations, 500-word max"
├── inputs/
└── outputs/
```

The project CLAUDE.md stacks on top of your main Cowork-Workspace CLAUDE.md. Both load. Project rules win when they conflict.

### Watch your context budget

Every file in `context/` loads at session start. Keep the total reasonable.

- **Target:** under ~5,000 tokens total across all context files
- **Warning sign:** sessions feel slow or Claude seems to skim your context
- **Fix:** consolidate files, trim redundancy, or move cross-cutting rules into per-project CLAUDE.md files

### Rule of thumb for what goes where

- **Root `context/`** — anything that applies to 70%+ of your work
- **Project `CLAUDE.md`** — anything that applies to just THIS project
- **Personal Preferences (settings)** — only stuff that must also work outside Cowork (Claude web, mobile, Claude Code)

---

## Using this workspace with Claude Code

The same folder structure works in Claude Code without changes. But the entry-point behavior differs:

| Tool | How it loads CLAUDE.md |
|---|---|
| Cowork | Uses the folder you SELECTED at launch. Files outside the mount are invisible. |
| Claude Code | Uses your current directory. Walks UP the tree automatically, reading every CLAUDE.md it finds. |

**What this means practically:**

- In Cowork: always select your Cowork-Workspace folder
- In Claude Code: you can `cd` into any project subfolder — parent CLAUDE.md still loads via directory walking

**Keep your CLAUDE.md portable:** use relative paths (`context/about-me.md`, not `/Users/...`), reference tools generically ("send the email" not "use the Gmail MCP"), and avoid UI-specific patterns like `computer://` links.

---

## Already have preferences? How to migrate

If you already have content in Personal Preferences or Cowork Global Instructions, pick one of three paths:

### Option A: Let Claude split your existing content into context files (easiest)

If you already have well-written preferences in settings, this is the fastest way to migrate. Claude reads your existing content and splits it across the right context files for you.

**Use `prompts/03-migrate-from-settings.md`** — it has the full instructions and the prompt to use. Open that file, follow the steps inside, and you'll be migrated in about 5 minutes.

### Option B: Fresh migration via interview (more thorough)

If your existing settings are messy or you want to rethink them, skip Option A and run the full setup interview from scratch. Use your old preferences as reference notes when answering questions, but let the interview produce the final files.

1. Copy your existing settings content into a temporary document (safety net)
2. Clear Personal Preferences and Cowork Global Instructions
3. Run Phases 1-4 of this guide normally
4. During the interview, reference your old preferences to give richer answers
5. Keep the temporary document for a week before deleting

### Option C: Keep what you have

If you're happy with your existing Personal Preferences and don't want to change them:

1. Leave Personal Preferences and Cowork Global Instructions alone
2. Run this guide, but during the interviews, skip questions that are already answered in your settings
3. Keep your workspace context files focused on workspace-specific info only (voice patterns, project conventions, tools) — not personal info already in settings

**Avoid at all costs:** putting the same info in both places. It doubles your context load, wastes tokens, and creates update headaches when things change.

---

## Troubleshooting

| Problem | Likely cause | Fix |
|---|---|---|
| Claude seems to have "forgotten" who I am | You launched Cowork from a project subfolder | Close and reopen, selecting your Cowork-Workspace folder |
| Files are saving to weird locations | Using full system paths in prompts | Use relative paths like `projects/my-project/outputs/` |
| Claude asks questions already in my context | CLAUDE.md doesn't reference the context folder | Open CLAUDE.md and confirm the "read all files in `context/`" instruction is there |
| Context files look outdated | You haven't updated them | Ask Claude: *"Update my [filename].md — [what changed]"* |
| Sessions feel slow | Context files are too long | Trim files; target under 5K tokens total |
| A new file in `context/` isn't being read | You haven't started a fresh session | Close and reopen Cowork — context loads at session start |

---

## Appendix A: Building from scratch (without the starter folder)

If you didn't use this starter and want to build the structure manually, paste this prompt into Claude after opening an empty workspace folder:

````
I'm setting up my Cowork workspace for the first time. Please create this exact structure in my current workspace folder:

1. Create a file at the top of my workspace folder called CLAUDE.md with this content:

---
# My Cowork Workspace

## Session start behavior
At the start of every session, read all files in the `context/` folder before responding. Use what you find to inform your work — don't announce it, just be informed by it.

## Folder structure
- `context/` — standing context about me. Update when preferences change.
- `projects/` — one subfolder per project. Each project is self-contained with its own CLAUDE.md, inputs, and outputs.

## Project conventions
When I start a new project:
- Create a new folder under `projects/` named after the project
- Inside it, create: CLAUDE.md (for project-specific rules), inputs/ (for source material), outputs/ (for deliverables)
- Save all work for that project inside its project folder — never outside it

## Environment notes
This workspace may be used in both Cowork and Claude Code. Use relative paths and generic tool references so instructions work in either environment.
---

2. Create a folder called `context/` with three empty files: about-me.md, my-voice.md, my-preferences.md

3. Create an empty folder called `projects/`

When done, list everything you created so I can verify.
````

---

## Appendix B: Separate interview prompts

Use these if you chose the alternative path in Phase 4.

### About-me interview

````
Interview me to fill out my about-me.md file. Use AskUserQuestion, one question at a time, covering:
- Who I am (role, industry, audience)
- How I work (tools, process, what "done" looks like)
- What good work looks like in my field
- What bad work looks like (things I hate)
- My rules and non-negotiables

Ask 10-12 questions total. If I say "that's enough," stop and compile what we have.

After the interview, write the result to `context/about-me.md` in under 1,500 tokens. Use clear section headers.
````

### My-voice interview (skip if you don't create content)

````
Interview me to fill out my my-voice.md file. Use AskUserQuestion covering:
- Tone and voice I use
- Words and phrases I always use
- Words and phrases I never use
- Examples of writing I love vs. hate
- Who my audience is and how I speak to them

Ask 6-8 questions. Save to `context/my-voice.md` in under 1,000 tokens.
````

### My-preferences interview

````
Interview me to fill out my my-preferences.md file. Use AskUserQuestion covering:
- Communication style (casual/formal, short/detailed)
- How I prefer to receive information (bullets, prose, tables)
- When I want you to push back vs. just do
- What I hate in AI responses
- Any other working-relationship rules

Ask 6-8 questions. Save to `context/my-preferences.md` in under 1,000 tokens.
````

---

## One-line summary

Create a folder, drop a CLAUDE.md in it, put your context files in a `context/` subfolder, and let Claude auto-load everything. That's the whole system. Everything else in this guide is implementation detail.
