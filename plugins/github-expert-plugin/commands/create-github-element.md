---
description: Create a new plugin, skill, or command in the GitHub Tech BM Second Brain
allowed-tools: Read, Write, Edit, Grep, Glob, Bash, WebSearch, WebFetch, Task
argument-hint: [element type and details — e.g., "skill finance-specialist in finance-expert-plugin"]
---

Create a new element in the GitHub Tech BM Second Brain repository for $ARGUMENTS using the github-repository-specialist skill.

## Context

The GitHub repository is Arthur's **Tech BM Second Brain** — a versioned backup of all plugins, skills, and commands used in the Claude/Cowork environment. It is NOT a code repository. It stores only three types of elements: **plugins**, **skills**, and **commands**.

GitHub is updated ONLY through the three github-expert-plugin commands (`/create-github-element`, `/update-github-element`, `/remove-github-element`). No other process should modify GitHub.

## Process

### Step 1 — Identify the Element Type
Determine what is being created. Only three types exist:
- **Plugin**: A full plugin directory with `.claude-plugin/plugin.json`, `README.md`, `skills/`, and `commands/`
- **Skill**: A `SKILL.md` file inside a plugin's `skills/[skill-name]/` directory
- **Command**: A `.md` file inside a plugin's `commands/` directory

### Step 2 — Read the Current GitHub Repository Structure
Use the `gh` CLI or GitHub API to inspect the current repo structure:
- List existing plugins (top-level directories)
- List skills and commands inside the target plugin
- Understand naming conventions, directory layout, and file formats already in use

### Step 3 — Read Reference Files for Format Compliance
Read at least one existing file of the same type from the repo to extract the exact format:
- For a plugin: read an existing `plugin.json` and `README.md`
- For a skill: read an existing `SKILL.md` from the same or similar plugin
- For a command: read an existing command `.md` from the same or similar plugin

### Step 4 — Prepare the New Element
Build the new element content following the patterns found in Step 3:
- Respect naming conventions (kebab-case directories and filenames)
- Follow the exact frontmatter structure (for skills and commands)
- Match the content depth and quality of existing elements

### Step 5 — Validation Gate
Before creating anything in GitHub, validate ALL of the following:
- [ ] Element type is one of: plugin, skill, or command
- [ ] Target plugin exists (unless creating a new plugin)
- [ ] No duplicate — an element with this name does not already exist
- [ ] File format matches the reference files read in Step 3
- [ ] Naming follows kebab-case convention
- [ ] For skills: frontmatter has `name`, `description`, `version`
- [ ] For commands: frontmatter has `description`, `allowed-tools`, `argument-hint`
- [ ] For plugins: `plugin.json` has `name`, `version`, `description`, `author`
- [ ] Content is complete and ready (no placeholders, no TODOs)

**If any check fails, STOP and resolve before proceeding.**

### Step 6 — Create in GitHub
Use the `gh` CLI to push the new files to the repository:
- Commit with a clear message: `"Add [type]: [name] to [plugin-name]"`
- Push to the main branch

### Step 7 — Update the Repository Main README.md
After creating the element, update the **main `README.md`** at the root of the repository (`arthurpaivar/TBM`). This file is the front page of the Tech BM Second Brain and must always reflect the current vault architecture.

Read the current `README.md` and update these specific sections:

1. **"Repository Structure"** — Update the plugin list and the skill/command counts (e.g., `[5 skills + 3 commands]`). If a new plugin was created, add a new bullet. If a skill or command was added to an existing plugin, increment its counts.
2. **"Plugin Suite Overview"** — Under the relevant plugin heading (e.g., `### 1. Technology Expert Plugin`), add the new skill to the **Skills** list or the new command to the **Commands** list. If creating a new plugin, add a new numbered subsection following the existing pattern (name, version, "Expert in", Skills list, Commands list).
3. **"Commands Reference"** — Update the total command count (e.g., `13 total commands`).
4. **Footer totals** — Update `**Total Expertise:** X plugins, Y skills, Z commands` at the bottom.
5. **"Version History"** — If the plugin version changed, add or update the version entry.
6. **"Last Updated"** — Set to today's date.

Commit with a clear message: `"Update README.md — add [type]: [name]"`
Push to the main branch.

### Step 8 — Sync the Claude Vault (Obsidian)
After successful GitHub creation, update the Obsidian vault to stay in sync.

**Important**: The Obsidian vault is organized **by element type** (flat), NOT by plugin. All skills from every plugin live together in `Skill/`, all commands in `Command/`, all plugins in `Plugin/`. This is different from GitHub where files are nested under their parent plugin directory.

Obsidian sync targets:
- **Plugin** → `Plugin/[Plugin Display Name].md` (e.g., `Plugin/Communication Expert Plugin.md`)
- **Skill** → `Skill/[skill-id].md` (e.g., `Skill/agile-specialist.md`)
- **Command** → `Command/[command-name].md` (e.g., `Command/draft-email.md`)

The Obsidian vault is the test environment. It must always reflect what is in GitHub. The sync direction is always **GitHub → Obsidian**, never the reverse.

## Output
Confirmation of the created element with:
- Element type and name
- GitHub commit reference
- Obsidian vault sync confirmation
- Validation checklist results (all passed)
