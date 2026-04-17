# New Project Setup Prompt

**What this does:** Creates a new self-contained project folder inside `projects/` with its own CLAUDE.md, inputs folder, and outputs folder. Also asks you a few questions about project-specific rules and fills in the project CLAUDE.md automatically.

**When to use it:** Every time you start a new project.

**How long it takes:** About 2-3 minutes.

**How to use it:** Copy everything between the lines below and paste it into Claude.

---

```
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
```

---

## After your project is set up

- Drop research, reference PDFs, spreadsheets, anything you want Claude to read → `inputs/`
- Work in progress → keep at the top of the project folder
- Finished deliverables → `outputs/`

The whole project stays together in one folder. If you ever need to archive, share, or hand off a project, just zip up that folder.

## A note on project CLAUDE.md files

The project CLAUDE.md stacks on top of your main workspace CLAUDE.md. Both load when you work inside that project. Project-specific rules WIN over workspace rules when they conflict — so use it to override defaults for just that project.
