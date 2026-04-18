# Setting Up Claude Cowork: A Step-by-Step Guide

A no-install, no-code setup for your Claude Cowork workspace. Works for total beginners, scales up to power users, and works the same way in Claude Code if you use both.

---

## What this is

A walkthrough for setting up a Claude Cowork workspace from scratch. You'll end up with:

- A dedicated workspace folder on your computer
- Context files that tell Claude who you are, how you work, and what "good" looks like
- A project structure that keeps every project self-contained and portable
- Zero plugins installed, zero command-line work required

Built for anyone, technical or not.

> **Two ways to use this guide.** The default path is **copy-paste prompts**: you create an empty folder and Claude builds the structure for you. No download needed. If you'd rather have everything pre-built, there's an **optional starter download** in [Phase 3](#phase-3-build-the-workspace-structure) (ZIP or GitHub template). Either path lands you at the same spot.

---

## The philosophy in 60 seconds

Claude Cowork automatically reads a file called `CLAUDE.md` when you open a folder. That auto-read is the only built-in feature. Everything else you've seen online (different folder layouts, naming conventions, templates) is just different opinions on what to put inside that file and which other files to put next to it.

This guide uses five principles:

1. **A CLAUDE.md file at the top of your workspace folder** loads automatically every session. No settings to configure.
2. **Context files in a `context/` folder** describe who you are, your voice, your preferences, and your current work situation.
3. **Each project is self-contained** with its own folder, rules, inputs, and outputs.
4. **Settings stay minimal.** Everything important lives in the workspace folder so it's portable.
5. **Works in Claude Code too.** The same folder structure is recognized by both tools.

One folder. One convention. Everything else is personal style.

---

## The five layers of context (good to know)

When Claude opens a conversation, it reads context from up to five places. This guide uses the bottom three:

| Layer | Scope | Portable? | This guide uses it? |
|---|---|---|---|
| 1. Claude Personal Preferences | All Claude products | No | Keep minimal or empty |
| 2. Cowork Global Instructions | All Cowork sessions | No | Keep empty |
| 3. Workspace CLAUDE.md | One workspace folder | Yes | Main place your rules live |
| 4. Project CLAUDE.md | One project subfolder | Yes | Per-project overrides |
| 5. Context files (via CLAUDE.md) | Referenced by workspace CLAUDE.md | Yes | Detailed context about you |

**Rule of thumb:** if it fits in your workspace folder, put it there. Only use settings fields for things that must also apply OUTSIDE Cowork.

---

## Before you start

### You'll need

- A computer (Mac or Windows)
- A Claude account
- The Claude desktop app installed (download from [claude.ai/download](https://claude.ai/download))
- About 30 minutes

### Check your existing settings (important)

This guide assumes a fresh setup. Before starting, check two places:

1. **Claude Personal Preferences** (Claude desktop app → Settings → Personal Preferences)
2. **Cowork Global Instructions** (Cowork Settings → Global Instructions)

**If both are empty:** proceed to [Phase 1](#phase-1-create-your-workspace-folder).

**If either has existing text in it:** see the [Already have preferences? How to migrate](#already-have-preferences-how-to-migrate) section before continuing. You'll need to decide whether to move that content into your new workspace setup or leave it where it is (and skip related interview questions later).

---

## Phase 1: Create your workspace folder

**Step 1. Pick a location.** Good options: Documents, Desktop, or a synced folder like Dropbox or iCloud. Avoid putting it inside other project folders.

**Step 2. Create the folder.**

1. Open Finder (Mac) or File Explorer (Windows)
2. Navigate to your chosen location
3. Right-click → New Folder
4. Name it `Cowork-Workspace` (no spaces or special characters keeps things simple later)

Leave the folder empty. Close the window.

---

## Phase 2: Open the folder in Cowork

**Step 3. Launch the Claude desktop app.** Find the Claude icon and open it.

**Step 4. Enter Cowork mode.** Look for a "Cowork" button, toggle, or menu option in the Claude interface.

**Step 5. Select your workspace folder.**

1. When prompted, click "Select Folder" or the folder-picker option
2. Navigate to `Cowork-Workspace`
3. Click "Select" or "Open"

**Check it worked:** type *"what folder am I working in?"* Claude should respond with the path to your Cowork-Workspace folder.

> **Critical habit from day one:** ALWAYS select your `Cowork-Workspace` folder, never a project subfolder inside it. This is the single most important rule. If you accidentally open a subfolder, Claude won't load your global context and will seem to "forget" who you are.

---

## Phase 3: Build the workspace structure

Two methods. Pick one. They land in the same spot.

### Method A: Have Claude build it for you (default, no download)

This is the recommended path. Copy the prompt below into Claude. Takes about 30 seconds.

````
I'm setting up my Cowork workspace for the first time. Please create this exact structure in my current workspace folder:

1. Create a file at the top of my workspace folder called CLAUDE.md with this content:

---
# My Cowork Workspace

## Session start behavior
At the start of every session, read all files in the `context/` folder before responding. Use what you find to inform your work. Don't announce it, just be informed by it.

## Folder structure
- `context/`: standing context about me. Update when preferences change.
- `projects/`: one subfolder per project. Each project is self-contained with its own CLAUDE.md, inputs, and outputs.

## Project conventions
When I start a new project:
- Create a new folder under `projects/` named after the project
- Inside it, create: CLAUDE.md (for project-specific rules), inputs/ (for source material), outputs/ (for deliverables)
- Save all work for that project inside its project folder, never outside it

## Environment notes
This workspace may be used in both Cowork and Claude Code. Use relative paths and generic tool references so instructions work in either environment.
---

2. Create a folder called `context/` with four empty files: about-me.md, my-work.md, my-voice.md, my-preferences.md

3. Create an empty folder called `projects/`

When done, list everything you created so I can verify.
````

### Method B: Download the pre-built starter (optional shortcut)

If you'd rather skip the prompt and have everything ready instantly, including all the prompt files saved locally for future use:

1. At the top of this repo, click the green **"Code"** button → **"Download ZIP"** *(or "Use this template" if you want your own GitHub copy)*
2. Unzip the download. Open the unzipped folder, select all the files and folders *inside* it, and move them into your `Cowork-Workspace` folder. Don't drop the whole unzipped folder in, only its contents.
3. Restart your Cowork session so it picks up the new files

### Verify either method worked

**Step 6. Check your folder.** Open it in Finder (Mac) or File Explorer (Windows). Either method should produce at minimum:

```
Cowork-Workspace/
├── CLAUDE.md
├── context/
│   ├── about-me.md
│   ├── my-work.md
│   ├── my-voice.md
│   └── my-preferences.md
└── projects/
```

If you used [Method B](#method-b-download-the-pre-built-starter-optional-shortcut), you'll *also* see `README.md`, `START-HERE.md`, `prompts/`, `LICENSE`, and `projects/README.md`. Both are valid setups.

---

## Phase 4: Fill out your context files

**Step 7. Run the setup interview.** Copy the prompt below into Claude. It will interview you for about 20 minutes and write your four context files automatically.

````
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
````

If you say "that's enough" at any point, Claude will stop and compile what you've shared so far.

> **Used [Method B](#method-b-download-the-pre-built-starter-optional-shortcut)?** This same prompt is saved at `prompts/01-setup-interview.md` for future use. Want a deeper, slower path? See [Appendix A](#appendix-a-separate-single-area-interview-prompts) for three separate single-area interview prompts.

---

## Phase 5: Test your setup

**Step 8. Start a fresh Cowork session.** Close your current session and reopen, selecting the same `Cowork-Workspace` folder.

**Step 9. Verify context loaded.** Copy the prompt below into Claude.

````
Run a setup verification on my Cowork workspace. Check the following and report back:

1. Did you read CLAUDE.md at the workspace level? Confirm what folder I'm in.

2. Did you read the files in `context/`? Tell me what you learned about:
   - Who I am (from about-me.md)
   - My current work situation (from my-work.md)
   - My voice (from my-voice.md, if filled in)
   - My preferences (from my-preferences.md)

3. List any context files that appear empty or contain only the original placeholder/stub content.

4. List the projects (if any) you can see in `projects/`.

5. Flag any obvious problems, missing files, contradictions in my context, or anything that looks misconfigured.

Be honest. If something isn't working, tell me clearly so I can fix it.
````

Claude should report back specifics: your role, preferences, tone, and flag any problems. If you get generic answers, see the [Troubleshooting](#troubleshooting) table at the end of this guide.

---

## Phase 6: Start your first real project

**Step 10. Set up a new project.** Copy the prompt below into Claude.

````
I'm starting a new project. Please help me set it up.

1. Ask me the project name, then create a folder with that name inside `projects/`.

2. Inside the new project folder, create:
   - A CLAUDE.md file (you'll fill this in from my answers below)
   - An empty `inputs/` folder (for source material, research, references)
   - An empty `outputs/` folder (for finished deliverables)

3. Ask me these questions using AskUserQuestion, ONE at a time. Skip any I say "N/A" to:
   - What's this project about in 1-2 sentences?
   - Who's the audience for the outputs?
   - Any tone or voice rules that differ from my defaults? (e.g., "formal, no contractions")
   - Any formatting rules? (e.g., "cite sources APA-style", "keep under 500 words")
   - Anything else Claude should know or do differently for this project?

4. Write my answers into the project's CLAUDE.md in clear sections. Keep it short.

5. When done, confirm by showing me:
   - The folder structure you created
   - A summary of the project-specific rules
   - A reminder that inputs go in `inputs/` and finished work goes in `outputs/`
````

Takes about 2-3 minutes total.

**Where to put files as you work:**

- Research, reference PDFs, source spreadsheets → project's `inputs/` folder
- Drafts and work-in-progress → keep at the top of the project folder
- Finished, ready-to-ship deliverables → project's `outputs/` folder

The whole project stays together. If you need to hand it off or archive it, zip up the project folder and you have everything.

---

## Phase 7: Ongoing habits

Three habits that keep this system working:

1. **Always select your Cowork-Workspace folder when launching Cowork.** Never select a project subfolder. Your Cowork-Workspace folder is where your global context lives. If you start inside a project folder instead, Claude won't see your context files.
2. **Update context files when things change.** New role, new team, new tool? Just tell Claude: *"Update my my-work.md, I'm on the Payments team now."* The `my-work.md` file is the one that churns most, rewrite it any time your job changes.
3. **Keep context files tight.** If any one file gets over 2,000 words, trim it. Long context files slow down every session.

---

## Advanced setup

### Adding new context files

Drop a new `.md` file into `context/`. Claude picks it up automatically at the next session start. The instruction "read all files in `context/`" handles any number of files. No CLAUDE.md edits required.

Common files users add as they grow:

- `technical-preferences.md`: coding, testing, security, version control rules
- `industry-terms.md`: glossary of jargon specific to your field
- `recurring-people.md`: team members, clients, or stakeholders Claude should know about
- `tools-and-systems.md`: the apps, platforms, and workflows you use daily
- `meeting-rhythms.md`: your standing meetings, recurring agendas, or workflows

### When you DO need to update CLAUDE.md

Only when you want Claude to treat one file differently from the others. For example:

- *"When writing for clients, use `brand-voice.md`. For personal posts, use `my-voice.md`."*
- *"Prioritize rules in `critical-rules.md` over everything else."*
- *"Only load `industry-terms.md` when the conversation involves technical topics."*

Without these explicit instructions, Claude treats all context files with equal importance, which is usually fine.

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

- **Target:** under about 4,000 words total across all context files (roughly 8 pages)
- **Warning sign:** sessions feel slow or Claude seems to skim your context
- **Fix:** consolidate files, trim redundancy, or move cross-cutting rules into per-project CLAUDE.md files

### Rule of thumb for what goes where

- **Root `context/`**: anything that applies to 70%+ of your work
- **Project `CLAUDE.md`**: anything that applies to just THIS project
- **Personal Preferences (settings)**: only stuff that must also work outside Cowork (Claude web, mobile, Claude Code)

---

## Using this workspace with Claude Code

The same folder structure works in Claude Code without changes. The difference is how each tool finds your files:

| Tool | How it loads CLAUDE.md |
|---|---|
| Cowork | Reads only the folder you SELECTED at launch. Files outside that folder are invisible. |
| Claude Code | Reads your current folder, then walks UP through its parent folders, loading every CLAUDE.md it finds along the way. |

**What this means practically:**

- In Cowork: always select your Cowork-Workspace folder at launch
- In Claude Code: you can start a session from inside any project subfolder. The parent Cowork-Workspace CLAUDE.md still loads because Claude Code walks up the folder tree automatically

**Keep your CLAUDE.md portable** by avoiding Cowork-specific shortcuts:
- Use relative paths like `context/about-me.md`, not full system paths like `/Users/your-name/...`
- Reference tools by what they do ("send the email") rather than by the specific Cowork integration ("use the Gmail MCP")
- Avoid Cowork-only link formats like `computer://` file links, which don't work in Claude Code

---

## Already have preferences? How to migrate

If you already have content in Personal Preferences or Cowork Global Instructions, pick one of three paths:

### Option A: Let Claude split your existing content into context files (easiest)

If you already have well-written preferences in settings, this is the fastest way to migrate. Claude reads your existing content and splits it across the right context files for you.

Copy the prompt below into Claude, REPLACE the `[PASTE YOUR EXISTING PREFERENCES HERE]` block with your actual Settings content first.

````
I'm migrating my existing Claude preferences into my workspace context files. Below is the content currently in my Personal Preferences and/or Cowork Global Instructions. Please:

1. Read through it carefully.

2. Split the content across my four context files based on what each section is about:
   - `context/about-me.md` → who I am as a professional, field, experience, how I think, my craft-level standards (stuff that stays true across jobs)
   - `context/my-work.md` → my current company, role, team, tools, customers, current priorities (stuff that changes when my job changes)
   - `context/my-voice.md` → how I write or speak, tone, words I use or avoid (skip if not applicable)
   - `context/my-preferences.md` → how I want you to communicate with me, formatting, working style, rules, error handling

3. Write each file to its location in `context/`. REPLACE any existing content in those files. If the `context/` folder doesn't exist, create it.

4. Check CLAUDE.md at the top of my workspace folder:
   - If it doesn't exist, create it with this content:
     ```
     # My Cowork Workspace

     ## Session start behavior
     At the start of every session, read all files in the `context/` folder before responding. Use what you find to inform your work. Don't announce it, just be informed by it.

     ## Folder structure
     - `context/`: standing context about me. Update when preferences change.
     - `projects/`: one subfolder per project. Each project is self-contained with its own CLAUDE.md, inputs, and outputs.

     ## Project conventions
     When I start a new project:
     - Create a new folder under `projects/` named after the project
     - Inside it, create: CLAUDE.md (for project-specific rules), inputs/ (for source material), outputs/ (for deliverables)
     - Save all work for that project inside its project folder, never outside it

     ## Environment notes
     This workspace may be used in both Cowork and Claude Code. Use relative paths and generic tool references so instructions work in either environment.
     ```
   - If it DOES exist, confirm it contains an instruction to read all files in `context/` at session start. If it doesn't, add one under a "Session start behavior" heading without removing anything else.

5. Show me a summary of what content went into each file, whether CLAUDE.md was created or updated, and flag anything that didn't clearly fit in one of the four context files so I can decide where it goes.

After you're done, I'll review the files. If they look good, I'll clear my Settings to avoid duplicate context.

Here's my existing content:
---
[PASTE YOUR EXISTING PREFERENCES HERE]
---
````

> If you used [Method B](#method-b-download-the-pre-built-starter-optional-shortcut) in [Phase 3](#phase-3-build-the-workspace-structure), this is also saved at `prompts/03-migrate-from-settings.md`.

### Option B: Fresh migration via interview (more thorough)

If your existing settings are messy or you want to rethink them, skip Option A and run the full setup interview from scratch. Use your old preferences as reference notes when answering questions, but let the interview produce the final files.

1. Copy your existing settings content into a temporary document (safety net)
2. Clear Personal Preferences and Cowork Global Instructions
3. Run [Phases 1-4](#phase-1-create-your-workspace-folder) of this guide normally
4. During the interview, reference your old preferences to give richer answers
5. Keep the temporary document for a week before deleting

### Option C: Keep what you have

If you're happy with your existing Personal Preferences and don't want to change them:

1. Leave Personal Preferences and Cowork Global Instructions alone
2. Run this guide, but during the interviews, skip questions that are already answered in your settings
3. Keep your workspace context files focused on workspace-specific info only (voice patterns, project conventions, tools), not personal info already in settings

**Avoid at all costs:** putting the same info in both places. It doubles what Claude has to read at the start of every session, makes conversations slower, and creates headaches when you update one copy and forget the other.

---

## Troubleshooting

| Problem | Likely cause | Fix |
|---|---|---|
| Claude seems to have "forgotten" who I am | You launched Cowork from a project subfolder | Close and reopen, selecting your Cowork-Workspace folder |
| Files are saving to weird locations | Using full system paths in prompts | Use relative paths like `projects/my-project/outputs/` |
| Claude asks questions already in my context | CLAUDE.md doesn't reference the context folder | Open CLAUDE.md and confirm the "read all files in `context/`" instruction is there |
| Context files look outdated | You haven't updated them | Ask Claude: *"Update my [filename].md, [what changed]"* |
| Sessions feel slow | Context files are too long | Trim files; target under about 4,000 words total |
| A new file in `context/` isn't being read | You haven't started a fresh session | Close and reopen Cowork. Context loads at session start |

---

## Appendix A: Separate single-area interview prompts

Use these instead of the combined [Phase 4](#phase-4-fill-out-your-context-files) interview if you'd rather take each area separately, one file at a time, with more questions and deeper exploration.

> **Prerequisite:** these prompts assume your workspace already has a CLAUDE.md that tells Claude to read all files in `context/` at session start (this gets set up in [Phase 3](#phase-3-build-the-workspace-structure)). If you skipped straight to Appendix A on a fresh workspace, run the [Phase 3](#phase-3-build-the-workspace-structure) Method A prompt first. Otherwise the context files you create here won't auto-load.

### About-me interview

````
Interview me to fill out my about-me.md file. This file captures my professional identity, the stuff that stays stable across jobs. Use AskUserQuestion, one question at a time, covering:
- The kind of work I do, my field, years of experience
- How I think and approach my work (approach, not tools)
- What good work looks like in my field
- What bad work looks like (things I hate)
- My rules and non-negotiables

Do NOT ask about my current company, team, or tools. That's for my-work.md.

Ask 8-10 questions total. If I say "that's enough," stop and compile what we have.

After the interview, write the result to `context/about-me.md` in under 1,500 tokens. Use clear section headers. If the `context/` folder doesn't exist yet, create it.

Then verify CLAUDE.md at the workspace root contains an instruction to read all files in `context/` at session start. If it does, you're done. If it doesn't, tell me so I can run the Phase 3 setup prompt before we continue.
````

### My-work interview

````
Interview me to fill out my my-work.md file. This file captures my current employment situation. Use AskUserQuestion, one question at a time, covering:
- My current company (name, what it does, stage/size)
- My role and scope (title, what I own, what I'm accountable for)
- My team (3-7 key collaborators by name with a one-line descriptor each)
- Tools I use daily (software, platforms)
- Who my customers or users are
- What I'm focused on right now (current goals, quarterly priorities)

Ask 6-8 questions total. If I say "that's enough," stop and compile what we have.

After the interview, write the result to `context/my-work.md` in under 1,000 tokens. Use clear section headers. If the `context/` folder doesn't exist yet, create it.

Then verify CLAUDE.md at the workspace root contains an instruction to read all files in `context/` at session start. If it does, you're done. If it doesn't, tell me so I can run the Phase 3 setup prompt before we continue.
````

### My-voice interview (skip if you don't create content)

````
Interview me to fill out my my-voice.md file. Use AskUserQuestion covering:
- Tone and voice I use
- Words and phrases I always use
- Words and phrases I never use
- Examples of writing I love vs. hate
- Who my audience is and how I speak to them

Ask 6-8 questions. Save to `context/my-voice.md` in under 1,000 tokens. If the `context/` folder doesn't exist yet, create it.

Then verify CLAUDE.md at the workspace root contains an instruction to read all files in `context/` at session start. If it does, you're done. If it doesn't, tell me so I can run the Phase 3 setup prompt before we continue.
````

### My-preferences interview

````
Interview me to fill out my my-preferences.md file. Use AskUserQuestion covering:
- Communication style (casual/formal, short/detailed)
- How I prefer to receive information (bullets, prose, tables)
- When I want you to push back vs. just do
- What I hate in AI responses
- Any other working-relationship rules

Ask 6-8 questions. Save to `context/my-preferences.md` in under 1,000 tokens. If the `context/` folder doesn't exist yet, create it.

Then verify CLAUDE.md at the workspace root contains an instruction to read all files in `context/` at session start. If it does, you're done. If it doesn't, tell me so I can run the Phase 3 setup prompt before we continue.
````

---

## One-line summary

Create a folder, drop a CLAUDE.md in it that tells Claude to read all files in `context/` at session start, put your context files in that `context/` subfolder, and let Claude auto-load everything. That's the whole system. Everything else in this guide is implementation detail.
