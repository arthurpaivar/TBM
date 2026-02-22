---
description: Update a plugin, skill, or command in the GitHub Tech BM Second Brain
allowed-tools: Read, Write, Edit, Grep, Glob, Bash, WebSearch, WebFetch, Task
argument-hint: [element type, name, and what changed — e.g., "skill agile-specialist in technology-expert-plugin"]
---

Update an existing element in the GitHub Tech BM Second Brain repository for $ARGUMENTS using the github-repository-specialist skill.

## Context

The GitHub repository is Arthur's **Tech BM Second Brain** — a versioned backup of all plugins, skills, and commands used in the Claude/Cowork environment. It is NOT a code repository. It stores only three types of elements: **plugins**, **skills**, and **commands**.

This is the **primary command** Arthur uses to keep GitHub in sync with changes made directly in Claude/Cowork sessions. When Arthur updates a skill, command, or plugin during a session, this command pushes those changes to GitHub as the versioned source of truth.

GitHub is updated ONLY through the three github-expert-plugin commands (`/create-github-element`, `/update-github-element`, `/remove-github-element`). No other process should modify GitHub.

## Process

### Step 1 — Identify the Element to Update
Determine the element type and exact location:
- **Plugin**: The plugin directory including `plugin.json`, `README.md`, and potentially its skills/commands
- **Skill**: A specific `skills/[skill-name]/SKILL.md` inside a plugin
- **Command**: A specific `commands/[command-name].md` inside a plugin

### Step 2 — Read the Current Version in GitHub
Use the `gh` CLI or GitHub API to read the current version of the element in GitHub:
- Download and read the existing file content
- Note the current version number (for skills and plugins)
- Identify the structure and formatting in use

### Step 3 — Read the Current Version in Claude/Cowork
Read the live version of the same element from the local plugin installation:
- Plugins are at: `.local-plugins/marketplaces/local-desktop-app-uploads/[plugin-name]/`
- Skills: `skills/[skill-name]/SKILL.md`
- Commands: `commands/[command-name].md`
- Plugin manifest: `.claude-plugin/plugin.json`

### Step 4 — Compare and Identify Changes
Compare the GitHub version (Step 2) with the Claude/Cowork version (Step 3):
- Identify every difference between the two versions
- Categorize changes: content updates, structural changes, new sections, removed sections
- Present a clear summary of what changed to Arthur

### Step 5 — Validation and Quality Check
Before pushing to GitHub, validate ALL of the following:
- [ ] Element type is one of: plugin, skill, or command
- [ ] The element exists in both GitHub and Claude/Cowork
- [ ] File format is preserved (frontmatter structure intact)
- [ ] Naming conventions are respected (kebab-case)
- [ ] For skills: frontmatter has `name`, `description`, `version`
- [ ] For commands: frontmatter has `description`, `allowed-tools`, `argument-hint`
- [ ] For plugins: `plugin.json` has `name`, `version`, `description`, `author`
- [ ] No placeholders or TODOs remain in the content
- [ ] The updated content is consistent with the plugin's overall structure
- [ ] If a skill changed, commands referencing it still make sense
- [ ] If a command changed, the referenced skill still exists
- [ ] README.md is updated if the change affects the plugin overview

**If any check fails, STOP and resolve before proceeding.**

### Step 6 — Push Update to GitHub
Use the `gh` CLI to push the updated files to the repository:
- Commit with a clear message: `"Update [type]: [name] in [plugin-name] — [brief change summary]"`
- If the plugin version should increment, update `plugin.json` version
- Update the plugin `README.md` if the change affects it
- Push to the main branch

### Step 7 — Update the Repository Main README.md
After pushing the update, check if the **main `README.md`** at the root of the repository (`arthurpaivar/TBM`) needs updating. This file is the front page of the Tech BM Second Brain and must always reflect the current vault architecture.

Read the current `README.md` and check if any of these sections need updating:

1. **"Repository Structure"** — If the update added or removed skills/commands within the plugin, update the counts (e.g., `[5 skills + 3 commands]`).
2. **"Plugin Suite Overview"** — If a skill or command name, description, or the plugin's "Expert in" summary changed, update the relevant lines under the plugin heading. If skills or commands were added/removed as part of the update, add/remove them from the lists.
3. **"Commands Reference"** — Update the total command count if commands were added or removed.
4. **"Example Interactions"** — If a command was renamed or its purpose changed, update or remove its example.
5. **Footer totals** — Update `**Total Expertise:** X plugins, Y skills, Z commands` if counts changed.
6. **"Version History"** — If the plugin version incremented, add or update the version entry.
7. **"Last Updated"** — Set to today's date.

If no README changes are needed (e.g., a minor content tweak inside a skill that doesn't affect names or counts), skip this step.

If changes are needed, commit with a clear message: `"Update README.md — reflect changes to [type]: [name]"`
Push to the main branch.

### Step 8 — Sync the Claude Vault (Obsidian)
After successful GitHub update, update the Obsidian vault to stay in sync.

**Important**: The Obsidian vault is organized **by element type** (flat), NOT by plugin. All skills from every plugin live together in `Skill/`, all commands in `Command/`, all plugins in `Plugin/`. This is different from GitHub where files are nested under their parent plugin directory.

Obsidian sync targets to update:
- **Plugin** → Update `Plugin/[Plugin Display Name].md` (e.g., `Plugin/Communication Expert Plugin.md`)
- **Skill** → Update `Skill/[skill-id].md` (e.g., `Skill/agile-specialist.md`)
- **Command** → Update `Command/[command-name].md` (e.g., `Command/draft-email.md`)
- When updating a **plugin** that added/removed skills or commands, also create/remove the corresponding files in `Skill/` and `Command/`

The Obsidian vault is the test environment. It must always reflect what is in GitHub. The sync direction is always **GitHub → Obsidian**, never the reverse.

## Output
Confirmation of the updated element with:
- Element type and name
- Summary of changes (before → after for key differences)
- GitHub commit reference
- Validation checklist results (all passed)
- Obsidian vault sync confirmation
