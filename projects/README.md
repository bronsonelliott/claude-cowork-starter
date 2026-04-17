# Projects

This folder is where each of your projects lives. Each project is self-contained in its own subfolder with its own CLAUDE.md, inputs, and outputs.

## Don't create project folders by hand

Use the prompt in `prompts/02-new-project.md` — it handles folder creation AND asks you a few questions to fill in the project's CLAUDE.md automatically. Much less work than doing it manually.

## What a project folder looks like

```
projects/
└── my-project-name/
    ├── CLAUDE.md          ← project-specific rules (tone, format, audience)
    ├── inputs/            ← research, references, source material
    │   ├── research.pdf
    │   └── data.xlsx
    └── outputs/           ← finished deliverables ready to share
        └── final-report.docx
```

## How the layered rules work

When you work inside a project folder, Claude reads TWO sets of rules:

1. Your main workspace CLAUDE.md (who you are, your global preferences)
2. The project's CLAUDE.md (this specific project's overrides)

Both apply. The project rules win when they conflict. So use project CLAUDE.md for project-specific things like "formal tone for this client" or "always cite sources APA-style for this project."

## A good habit

When you finish a project, consider zipping the whole project folder and storing it somewhere for reference. Because everything lives together — inputs, working files, outputs, project rules — you have a complete record of the work.
