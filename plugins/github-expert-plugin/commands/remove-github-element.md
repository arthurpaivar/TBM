---
description: Remove a plugin, skill, or command from the GitHub Tech BM Second Brain
allowed-tools: Read, Write, Edit, Grep, Glob, Bash, WebSearch, WebFetch, Task
argument-hint: [element type and identifier — e.g., "command draft-email from communication-expert-plugin"]
---

Remove an element from the GitHub Tech BM Second Brain repository for $ARGUMENTS using the github-repository-specialist skill.

## Context

The GitHub repository is Arthur's **Tech BM Second Brain** — a versioned backup of all plugins, skills, and commands used in the Claude/Cowork environment. It is NOT a code repository. It stores only three types of elements: **plugins**, **skills**, and **commands**.

GitHub is updated ONLY through the three github-expert-plugin commands (`/create-github-element`, `/update-github-element`, `/remove-github-element`). No other process should modify GitHub.

## GitHub Access Method

**CRITICAL — Read this before any GitHub operation.**

The Cowork VM does NOT have the `gh` CLI installed and `api.github.com` is blocked by the VM proxy. Do NOT attempt `gh` commands, `curl`/`python requests` to `api.github.com`, or any GitHub REST API calls — they will all fail.

The ONLY working method is `git clone` with the token embedded in the URL:

```bash
git clone https://<TOKEN>@github.com/arthurpaivar/TBM.git /tmp/TBM
```

Arthur's GitHub Personal Access Token is required. If not already known from the current session, **ask Arthur for it**. Once cloned, all read/write operations happen on the local `/tmp/TBM` clone. After making changes, commit and push:

```bash
cd /tmp/TBM && git add . && git commit -m "message" && git push
```

If the repo is already cloned in this session, do a `git pull` in `/tmp/TBM` before starting.

## Process

### Step 1 — Identify What to Remove
Determine the element type and exact location:
- **Plugin**: An entire plugin directory (`.claude-plugin/`, `README.md`, `skills/`, `commands/`)
- **Skill**: A specific `skills/[skill-name]/SKILL.md` inside a plugin
- **Command**: A specific `commands/[command-name].md` inside a plugin

### Step 2 — Read the Current State in GitHub
From the local `/tmp/TBM` clone (clone or `git pull` first):
- Confirm the element exists in the repository
- Read the element content so you can show Arthur exactly what will be removed
- For plugins: list all skills and commands that will be removed together

### Step 3 — First Confirmation: Show What Will Be Removed
Present to Arthur a clear summary of what will be deleted:
- Element type, name, and location in the repository
- For plugins: list every skill and command inside it
- File paths that will be removed
- Any downstream impact (e.g., commands that reference a skill being removed)

**Ask Arthur to confirm: "Are you sure you want to remove [element]? This will delete [details]."**

### Step 4 — Second Confirmation: Final Safety Check
After Arthur confirms once, ask one final time:
- "Confirmed: I will permanently remove [element] from the GitHub repository. The Obsidian vault will also be updated. Proceed? (yes/no)"

**Do NOT proceed unless Arthur explicitly says yes to both confirmations.**

### Step 5 — Remove from GitHub
Delete the files from the local `/tmp/TBM` clone, then commit and push:
- `git rm` the files to be removed
- Commit with a clear message: `"Remove [type]: [name] from [plugin-name]"`
- For plugins: also update the repository root if needed
- For skills/commands: update the parent plugin's `README.md` to reflect the removal
- `git push` to the main branch

### Step 6 — Update the Repository Main README.md
After removing the element, update the **main `README.md`** at the root of the repository (`arthurpaivar/TBM`). This file is the front page of the Tech BM Second Brain and must always reflect the current vault architecture.

Read the current `README.md` and update these specific sections:

1. **"Repository Structure"** — Update the plugin list and the skill/command counts (e.g., `[5 skills + 3 commands]`). If a plugin was removed, delete its bullet. If a skill or command was removed, decrement the parent plugin's counts.
2. **"Plugin Suite Overview"** — Under the relevant plugin heading (e.g., `### 1. Technology Expert Plugin`), remove the skill from the **Skills** list or the command from the **Commands** list. If removing an entire plugin, delete its full numbered subsection and renumber the remaining ones.
3. **"Commands Reference"** — Update the total command count (e.g., `13 total commands`).
4. **"Example Interactions"** — Remove any examples that reference the deleted command.
5. **Footer totals** — Update `**Total Expertise:** X plugins, Y skills, Z commands` at the bottom.
6. **"Version History"** — If the plugin version changed, update the version entry.
7. **"Last Updated"** — Set to today's date.

Commit with a clear message: `"Update README.md — remove [type]: [name]"`
Push to the main branch.

### Step 7 — Sync the Claude Vault (Obsidian)
After successful GitHub removal, update the Obsidian vault to stay in sync.

**Important**: The Obsidian vault is organized **by element type** (flat), NOT by plugin. All skills from every plugin live together in `Skill/`, all commands in `Command/`, all plugins in `Plugin/`. This is different from GitHub where files are nested under their parent plugin directory.

Obsidian sync targets to remove:
- **Plugin** → Delete `Plugin/[Plugin Display Name].md` (e.g., `Plugin/Communication Expert Plugin.md`)
- **Skill** → Delete `Skill/[skill-id].md` (e.g., `Skill/agile-specialist.md`)
- **Command** → Delete `Command/[command-name].md` (e.g., `Command/draft-email.md`)
- When removing a **plugin**, also remove all its skills from `Skill/` and all its commands from `Command/`

The Obsidian vault is the test environment. It must always reflect what is in GitHub. The sync direction is always **GitHub → Obsidian**, never the reverse.

## Output
Confirmation of the removed element with:
- Element type and name
- GitHub commit reference
- List of files deleted
- Obsidian vault sync confirmation
- Note: "This action is versioned in GitHub — you can roll back if needed."
