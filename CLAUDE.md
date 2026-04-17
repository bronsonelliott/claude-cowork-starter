# My Cowork Workspace

## Session start behavior
At the start of every session, read all files in the `context/` folder before responding. Use what you find to inform your work — don't announce it, just be informed by it.

## Folder structure
- `context/` — standing context about me. Update when preferences change.
- `projects/` — one subfolder per project. Each project is self-contained with its own CLAUDE.md, inputs, and outputs.
- `prompts/` — reusable prompts for setup, project creation, and other workflows.

## Project conventions
When I start a new project:
- Create a new folder under `projects/` named after the project
- Inside it, create: CLAUDE.md (for project-specific rules), inputs/ (for source material), outputs/ (for deliverables)
- Save all work for that project inside its project folder — never outside it

## Environment notes
This workspace may be used in both Cowork and Claude Code. Use relative paths and generic tool references so instructions work in either environment.
