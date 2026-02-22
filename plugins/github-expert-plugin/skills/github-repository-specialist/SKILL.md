---
name: github-repository-specialist
description: >
  This skill should be used when the user asks about "GitHub", "repository", "repo",
  "TBM", "Tech BM Second Brain", "sync to GitHub", "push to GitHub",
  "update GitHub", "create in GitHub", "remove from GitHub",
  "vault sync", "Obsidian sync", "backup plugins",
  "git clone", "git push", "GitHub token",
  "sync plugins", "push changes", "version backup",
  or needs help managing, syncing, or maintaining the TBM repository.
  Use whenever the user wants to create, update, or remove plugins, skills,
  or commands in the GitHub repository.
version: 2.0.0
---

# Skill — GitHub Repository Specialist

**Expert in managing the Tech BM Second Brain GitHub repository.** This skill provides comprehensive understanding of the TBM repository structure, element types (plugins, skills, commands), sync workflows between Claude/Cowork → GitHub → Obsidian, and the technical constraints of the Cowork VM environment. It serves as the knowledge base that the three GitHub commands (create, update, remove) orchestrate.

**Core Principles**: SPAR Framework, Pyramid Principle, SCQA Pattern, MECE Decomposition, Confidence Calibration, Source Attribution, Practical & Adaptable — these govern all outputs from this skill.

**Trigger keywords**: GitHub, repository, repo, TBM, Tech BM Second Brain, sync, push, backup, vault sync, Obsidian sync, git clone, git push, GitHub token, sync plugins, push changes, version backup.

## Section 1 — The Tech BM Second Brain

### 1.1 — What It Is

The GitHub repository `arthurpaivar/TBM` is Arthur's **Tech BM Second Brain** — a versioned backup of all plugins, skills, and commands used in the Claude/Cowork environment. It is NOT a code repository. It stores only three types of elements.

### 1.2 — The Three Element Types

| Element | What It Contains | Location in GitHub |
|---------|-----------------|-------------------|
| **Plugin** | `.claude-plugin/plugin.json`, `README.md`, `skills/`, `commands/` | `plugins/[plugin-name]/` |
| **Skill** | `SKILL.md` file | `plugins/[plugin-name]/skills/[skill-name]/SKILL.md` |
| **Command** | `.md` file | `plugins/[plugin-name]/commands/[command-name].md` |

### 1.3 — Repository Structure (GitHub — Nested by Plugin)

```
TBM/
├── README.md                          [Main vault architecture page]
├── plugins/
│   ├── technology-expert-plugin/
│   │   ├── .claude-plugin/plugin.json
│   │   ├── README.md
│   │   ├── skills/
│   │   │   ├── agile-specialist/SKILL.md
│   │   │   ├── ai-specialist/SKILL.md
│   │   │   ├── architecture-specialist/SKILL.md
│   │   │   ├── tech-delivery-specialist/SKILL.md
│   │   │   └── tech-strategy-advisory/SKILL.md
│   │   └── commands/
│   │       ├── explain-tech-concept.md
│   │       └── list-tech-references.md
│   ├── communication-expert-plugin/
│   ├── consulting-expert-plugin/
│   ├── finance-expert-plugin/
│   ├── ai-expert-plugin/
│   └── github-expert-plugin/
└── ...
```

### 1.4 — Obsidian Structure (Flat by Type)

```
Vault/
├── Plugin/
│   ├── Technology Expert Plugin.md
│   ├── Communication Expert Plugin.md
│   └── ...
├── Skill/
│   ├── agile-specialist.md
│   ├── ai-specialist.md
│   └── ...
└── Command/
    ├── explain-tech-concept.md
    ├── create-improve-email.md
    └── ...
```

**Critical distinction**: GitHub nests everything under plugin directories. Obsidian organizes everything flat by element type. All skills from every plugin live together in `Skill/`, all commands in `Command/`, all plugins in `Plugin/`.

## Section 2 — GitHub Access Method

**CRITICAL — The Cowork VM has specific technical constraints that must be respected.**

The `gh` CLI is NOT installed. `api.github.com` is blocked by the VM proxy. Python `requests` to GitHub API, `curl` to GitHub API, and MCP fetch tools all fail.

The **ONLY working method** is `git clone` with the Personal Access Token embedded in the URL:

```bash
git clone https://<TOKEN>@github.com/arthurpaivar/TBM.git /tmp/TBM
```

Once cloned, all operations happen locally on `/tmp/TBM`. After changes:

```bash
cd /tmp/TBM && git add . && git commit -m "message" && git push
```

If the repo is already cloned in the current session, start with `git pull` instead of cloning again.

Arthur's GitHub Personal Access Token is required for every session. If not already known, **ask Arthur for it** before attempting any GitHub operation.

### 2.1 — What NOT to Do

- Do NOT run `gh` commands — the CLI is not installed
- Do NOT use `curl` or `python requests` to `api.github.com` — it's proxy-blocked
- Do NOT use MCP fetch tools with GitHub API URLs — they block tokens
- Do NOT use WebFetch with `api.github.com` — it's blocked
- Do NOT waste time trying alternative access methods — `git clone` with token is the answer

## Section 3 — Sync Workflow

### 3.1 — Direction

The sync direction is always: **Claude/Cowork → GitHub → Obsidian**. Never the reverse.

### 3.2 — Source of Truth

| Environment | Role |
|------------|------|
| **Claude/Cowork** | Where Arthur works and makes changes during sessions |
| **GitHub** | The versioned backup and source of truth for all elements |
| **Obsidian** | The test environment that mirrors GitHub |

### 3.3 — Authorized Modification

The GitHub repository is updated ONLY through the three github-expert-plugin commands:

| Command | Purpose | Usage |
|---------|---------|-------|
| `/create-github-element` | Add new elements | New plugins, skills, or commands |
| `/update-github-element` | Sync changes | **Primary, most-used command** |
| `/remove-github-element` | Remove elements | Requires double confirmation |

No other process should modify GitHub.

### 3.4 — The Main README.md

The `README.md` at the root of the repository is the front page of the Tech BM Second Brain. It must always reflect the current vault architecture. After every create, update, or remove operation, check if these sections need updating:

1. **Repository Structure** — Plugin list, skill/command counts
2. **Plugin Suite Overview** — Plugin details, skill lists, command lists
3. **Commands Reference** — Total command count, command table
4. **Example Interactions** — Command usage examples
5. **Footer totals** — Total plugins, skills, commands
6. **Version History** — Plugin version entries
7. **Last Updated** — Today's date

## Section 4 — Validation Standards

### 4.1 — For Plugins

- `plugin.json` has `name`, `version`, `description`, `author`
- `README.md` describes the plugin's purpose, skills, and commands
- Directory uses kebab-case naming

### 4.2 — For Skills

- Frontmatter has `name`, `description`, `version`
- Content includes sections with domain methodology, output patterns, quality checks
- Trigger keywords are specific and non-overlapping
- Communication Protocol section present

### 4.3 — For Commands

- Frontmatter has `description`, `allowed-tools`, `argument-hint`
- Layered What/How/Why structure
- References the correct parent skill(s)
- No placeholders or TODOs remain

### 4.4 — General

- All naming follows kebab-case convention
- Content is complete and production-ready
- No software development references (PRs, issues, CI/CD) unless specifically relevant
- Consistent with the plugin's overall structure and other plugins in the vault

## Section 5 — Communication Protocol

### Opening (The Result)
Lead with what happened: "Sync complete — [X] elements [created/updated/removed] in [plugin-name]." The reader should know the outcome before any details.

### Body (The Details)
Show what changed: file paths, version numbers, commit references, README updates. Keep it factual and scannable — a table or bullet list of changes, not a narrative.

### Conclusion (The Verification)
Confirm that all validation checks passed, Obsidian is synced, and the main README reflects the current state. Flag any anomalies.

## Output Patterns

### Sync Summary

```
═══════════════════════════════════════════════════════
SYNC COMPLETE: [scope]
═══════════════════════════════════════════════════════

CHANGES:
• [Created/Updated/Removed]: [element type] — [name] in [plugin]
• ...

───────────────────────────────────────────────────────
DETAILS
───────────────────────────────────────────────────────
GitHub: Commit [hash] pushed to main
README: [Updated sections / No changes needed]
Obsidian: [X] files synced to [Plugin/Skill/Command]
Validation: All checks passed
═══════════════════════════════════════════════════════
```

### Element Inventory

```
═══════════════════════════════════════════════════════
CURRENT VAULT: X plugins, Y skills, Z commands
═══════════════════════════════════════════════════════

PLUGINS:
1. [Plugin Name] — [skill count] skills, [command count] commands
2. ...

───────────────────────────────────────────────────────
TOTAL: X plugins | Y skills | Z commands
═══════════════════════════════════════════════════════
```

## Quality Checks

- [ ] Have I used `git clone` with token (not `gh` CLI or API)?
- [ ] Have I read the current GitHub state before making changes?
- [ ] Have I validated all elements against the standards in Section 4?
- [ ] Have I updated the main README.md if counts or names changed?
- [ ] Have I synced the Obsidian vault (flat by type, not nested)?
- [ ] Is the sync direction correct (Claude/Cowork → GitHub → Obsidian)?
- [ ] Are there zero software development references where they don't belong?

---

**Confidence Calibration**: High confidence for standard sync operations, element creation, and validation. Medium confidence for complex multi-plugin bulk syncs — recommend step-by-step verification.

**Triggers**: Activate when user requests GitHub sync, repository management, element creation/update/removal, or vault architecture queries.
