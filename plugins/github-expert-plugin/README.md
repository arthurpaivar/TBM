# GitHub Expert Plugin

Specialist in managing the Tech BM Second Brain GitHub repository — the versioned backup of all plugins, skills, and commands used in the Claude/Cowork environment.

## Purpose

This plugin is the **only authorized way** to modify the GitHub repository (`arthurpaivar/TBM`). It provides three commands to create, update, and remove elements (plugins, skills, commands), and ensures that every change is also reflected in the repository's main README.md and synced to the Obsidian vault.

## Skills

| Skill | Focus Areas |
|-------|-------------|
| **GitHub Repository Specialist** | TBM repository structure, three element types (plugins/skills/commands), git clone with token access method, Claude/Cowork → GitHub → Obsidian sync workflow, validation standards |

## Commands

| Command | What It Does | Key Feature |
|---------|-------------|-------------|
| **create-github-element** | Add a new plugin, skill, or command to the TBM repository | Validation gate before creation, README cascade |
| **update-github-element** | Sync changes from Claude/Cowork to GitHub | **Primary command** — compares both versions, validates, pushes delta |
| **remove-github-element** | Remove a plugin, skill, or command | Double confirmation safety gate, cascading impact assessment |

## Key Concepts

| Concept | Detail |
|---------|--------|
| **Repository** | `arthurpaivar/TBM` — stores plugins, skills, and commands. NOT a code repository |
| **GitHub Access** | `git clone` with token in URL — the only working method in Cowork VM. No `gh` CLI or GitHub API |
| **Sync Direction** | Claude/Cowork → GitHub → Obsidian. Never the reverse |
| **Obsidian Structure** | Flat by type (`Plugin/`, `Skill/`, `Command/`), unlike GitHub which nests under plugin directories |

## Communication Protocol

All outputs follow: **Opening** (the result — what happened) → **Body** (the details — files, commits, changes) → **Conclusion** (verification — validation passed, Obsidian synced, README updated).

## How to Use

Each command activates with its slash command:

- `/create-github-element skill finance-specialist in finance-expert-plugin` → Creates the skill in GitHub + Obsidian
- `/update-github-element consulting-expert-plugin` → Syncs all changes to GitHub + Obsidian
- `/remove-github-element command draft-email from communication-expert-plugin` → Removes with double confirmation

## Setup

No configuration needed. Install the plugin and all commands are available automatically. Arthur's GitHub Personal Access Token is required at runtime for each session.
