---
description: Remove a plugin, skill, or command from the GitHub Tech BM Second Brain
allowed-tools: Read, Write, Edit, Grep, Glob, Bash, WebSearch, WebFetch, Task
argument-hint: [element type and identifier — e.g., "command draft-email from communication-expert-plugin"]
---

Remove an element from the GitHub Tech BM Second Brain repository for $ARGUMENTS using the github-repository-specialist skill.

**This command requires DOUBLE CONFIRMATION before any deletion. No exceptions.**

## Layer 1 — Knowledge Loading & Element Identification

**What:** Load the skill and determine what is being removed.
**How:**
1. Read the github-repository-specialist skill from this plugin — it contains the repository structure, access method, validation standards, and sync workflow
2. Parse $ARGUMENTS to identify:
   - **Element type**: Plugin, skill, or command
   - **Target plugin**: Which plugin contains the element
   - **Element name**: The specific element to remove

**Why:** Removal is permanent in the working tree (though versioned in git history). Loading the skill ensures correct access method and understanding of cascading impacts.

## Layer 2 — Read Current State & Assess Impact

**What:** Confirm the element exists and assess what will be affected.
**How:**
1. Clone the repo (or `git pull` if already cloned) following the access method in the skill
2. If the token is not known, **ask Arthur for it** before proceeding
3. Confirm the element exists in the repository
4. Read the element content to show Arthur exactly what will be removed
5. Assess cascading impact:
   - For plugins: list ALL skills and commands inside it that will be removed
   - For skills: check if any commands reference this skill
   - For commands: check if any other commands or README reference it

**Why:** Showing the full impact before confirmation prevents accidental data loss. A plugin removal cascades to every skill and command inside it.

## Layer 3 — Double Confirmation

**What:** Get explicit confirmation from Arthur — twice.
**How:**

**First confirmation**: Present a clear summary:
- Element type, name, and location
- For plugins: list every skill and command that will be removed
- File paths affected
- Any downstream impact

Ask: "Are you sure you want to remove [element]? This will delete [details]."

**Second confirmation**: After Arthur confirms once:
- "Confirmed: I will permanently remove [element] from the GitHub repository. The Obsidian vault will also be updated. Proceed? (yes/no)"

**Do NOT proceed unless Arthur explicitly says yes to BOTH confirmations.**

**Why:** Double confirmation is the safety gate. Removal is versioned in git (rollback possible), but the friction of double confirmation prevents hasty deletions.

## Layer 4 — Remove from GitHub & Update README

**What:** Delete files, commit, push, and update the main README.
**How:**
1. `git rm` the files from `/tmp/TBM`
2. If removing a skill or command: update the parent plugin's `README.md` to reflect the removal
3. Commit with message: `"Remove [type]: [name] from [plugin-name]"` and `git push`
4. Read the main `README.md` and update: Repository Structure counts, Plugin Suite Overview, Commands Reference, Example Interactions, Footer totals, Version History, Last Updated
5. Commit and push the README update: `"Update README.md — remove [type]: [name]"`

**Why:** Both the plugin README and the main repository README must be updated to reflect the removal. Stale references create confusion.

## Layer 5 — Sync Obsidian & Deliver

**What:** Remove from Obsidian vault and confirm the operation.
**How:**
1. Delete the corresponding files from Obsidian in the **flat by type** structure:
   - Plugin → delete `Plugin/[Display Name].md`
   - Skill → delete `Skill/[skill-id].md`
   - Command → delete `Command/[command-name].md`
   - For plugin removal: also delete all its skills from `Skill/` and commands from `Command/`
2. Deliver using the Sync Summary output pattern from the skill
3. Include note: "This action is versioned in GitHub — rollback is possible if needed."

**Why:** Obsidian must mirror GitHub. Confirming rollback capability provides peace of mind for irreversible-feeling operations.
