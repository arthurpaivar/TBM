---
description: Update a plugin, skill, or command in the GitHub Tech BM Second Brain
allowed-tools: Read, Write, Edit, Grep, Glob, Bash, WebSearch, WebFetch, Task
argument-hint: [element type, name, and what changed — e.g., "skill agile-specialist in technology-expert-plugin"]
---

Update an existing element in the GitHub Tech BM Second Brain repository for $ARGUMENTS using the github-repository-specialist skill.

**This is the primary command — used most frequently to keep GitHub in sync with changes made in Claude/Cowork sessions.**

## Layer 1 — Knowledge Loading & Element Identification

**What:** Load the skill and determine what is being updated.
**How:**
1. Read the github-repository-specialist skill from this plugin — it contains the repository structure, access method, validation standards, and sync workflow
2. Parse $ARGUMENTS to identify:
   - **Element type**: Plugin, skill, or command
   - **Target plugin**: Which plugin contains the element
   - **Element name**: The specific element to update
   - **Change scope**: What changed (if specified — otherwise, discover through comparison)

**Why:** The skill contains the GitHub access method and all validation rules. Loading it first ensures correct workflow.

## Layer 2 — Read Both Versions

**What:** Get the current state from both GitHub and Claude/Cowork.
**How:**
1. Clone the repo (or `git pull` if already cloned) following the access method in the skill
2. If the token is not known, **ask Arthur for it** before proceeding
3. Read the **GitHub version** from `/tmp/TBM/plugins/[plugin-name]/...`
4. Read the **Claude/Cowork version** from `/mnt/.local-plugins/marketplaces/local-desktop-app-uploads/[plugin-name]/...`
5. Compare the two versions and identify every difference

**Why:** Comparing both versions reveals exactly what changed. This prevents partial syncs and ensures the full delta is captured.

## Layer 3 — Validate & Push

**What:** Validate the updated content and push to GitHub.
**How:**
1. Run the validation gate (from skill Section 4):
   - [ ] Element exists in both GitHub and Claude/Cowork
   - [ ] File format preserved (frontmatter structure intact)
   - [ ] Naming conventions respected (kebab-case)
   - [ ] Frontmatter fields complete for the element type
   - [ ] No placeholders or TODOs remain
   - [ ] Content consistent with the plugin's overall structure
   - [ ] If a skill changed, commands referencing it still make sense
   - [ ] If a command changed, the referenced skill still exists

**If any check fails, STOP and resolve before proceeding.**

2. Write the updated files to `/tmp/TBM`
3. If plugin version should increment, update `plugin.json`
4. Update the plugin's own `README.md` if affected
5. `git add`, commit with message: `"Update [type]: [name] in [plugin-name] — [brief change summary]"`, and `git push`

**Why:** Validation before push catches inconsistencies — like a command referencing a skill that was renamed.

## Layer 4 — Update Main README & Sync Obsidian

**What:** Update the repository README and sync Obsidian.
**How:**
1. Read the main `README.md` at the repository root
2. Check if any sections need updating (Section 3.4 of the skill): Repository Structure counts, Plugin Suite Overview details, Commands Reference, Footer totals, Version History, Last Updated
3. If changes needed: commit and push separately. If not: skip
4. Sync Obsidian vault in **flat by type** structure:
   - Plugin → `Plugin/[Display Name].md`
   - Skill → `Skill/[skill-id].md`
   - Command → `Command/[command-name].md`
   - If a plugin update added/removed skills or commands, also create/remove the corresponding Obsidian files
5. Deliver using the Sync Summary output pattern from the skill

**Why:** The main README and Obsidian vault must always mirror the current GitHub state. Skipping the README update when nothing relevant changed avoids noise commits.
