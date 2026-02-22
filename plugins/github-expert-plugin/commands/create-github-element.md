---
description: Create a new plugin, skill, or command in the GitHub Tech BM Second Brain
allowed-tools: Read, Write, Edit, Grep, Glob, Bash, WebSearch, WebFetch, Task
argument-hint: [element type and details — e.g., "skill finance-specialist in finance-expert-plugin"]
---

Create a new element in the GitHub Tech BM Second Brain repository for $ARGUMENTS using the github-repository-specialist skill.

## Layer 1 — Knowledge Loading & Element Identification

**What:** Load the skill and determine what is being created.
**How:**
1. Read the github-repository-specialist skill from this plugin — it contains the repository structure, access method, validation standards, and sync workflow
2. Parse $ARGUMENTS to identify:
   - **Element type**: Plugin, skill, or command (only three types exist)
   - **Target plugin**: Which plugin this element belongs to (unless creating a new plugin)
   - **Element name**: The kebab-case identifier

**Why:** The skill contains the GitHub access method (git clone with token — the ONLY working method in Cowork VM) and all validation standards. Loading it first prevents wasted effort from wrong access methods.

## Layer 2 — Read Current State

**What:** Clone the repository and understand the current structure.
**How:**
1. Clone the repo (or `git pull` if already cloned in this session) following the access method in the skill
2. If the token is not known, **ask Arthur for it** before proceeding
3. List existing plugins under `plugins/`
4. List skills and commands inside the target plugin
5. Read at least one existing element of the same type to extract the exact format and quality standard

**Why:** You need to confirm the element doesn't already exist (no duplicates) and understand the format conventions before creating anything.

## Layer 3 — Prepare & Validate

**What:** Build the new element content and validate it before writing to GitHub.
**How:**
1. Prepare the element content following the patterns found in Layer 2:
   - Kebab-case naming, correct frontmatter structure, production-ready content
2. Run the validation gate (from skill Section 4):
   - [ ] Element type is plugin, skill, or command
   - [ ] Target plugin exists (unless creating a new plugin)
   - [ ] No duplicate with the same name
   - [ ] For skills: frontmatter has `name`, `description`, `version`
   - [ ] For commands: frontmatter has `description`, `allowed-tools`, `argument-hint`
   - [ ] For plugins: `plugin.json` has `name`, `version`, `description`, `author`
   - [ ] Content is complete — no placeholders or TODOs

**If any check fails, STOP and resolve before proceeding.**

**Why:** Validation before creation prevents broken elements in the repository. Once pushed to GitHub, mistakes require additional cleanup commits.

## Layer 4 — Create in GitHub & Update README

**What:** Write files, commit, push, and update the main README.
**How:**
1. Write the new files to `/tmp/TBM` in the correct locations
2. `git add`, commit with message: `"Add [type]: [name] to [plugin-name]"`, and `git push`
3. Read the main `README.md` at the repository root
4. Update the sections specified in the skill (Section 3.4): Repository Structure, Plugin Suite Overview, Commands Reference, Footer totals, Version History, Last Updated
5. Commit and push the README update separately: `"Update README.md — add [type]: [name]"`

**Why:** The main README is the front page of the Tech BM Second Brain. It must always reflect the current state. A separate commit keeps the history clean.

## Layer 5 — Sync Obsidian & Deliver

**What:** Sync the Obsidian vault and confirm the operation.
**How:**
1. Write the element to the Obsidian vault in the **flat by type** structure:
   - Plugin → `Plugin/[Display Name].md`
   - Skill → `Skill/[skill-id].md`
   - Command → `Command/[command-name].md`
2. Deliver using the Sync Summary output pattern from the skill

**Why:** Obsidian must mirror GitHub. The flat structure is different from GitHub's nested structure — skills from all plugins live together in `Skill/`, commands in `Command/`.
