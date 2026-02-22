# GitHub Expert Plugin

Specialist in managing the Tech BM Second Brain GitHub repository — the versioned backup of all plugins, skills, and commands used in the Claude/Cowork environment.

## Purpose

This plugin is the **only authorized way** to modify the GitHub repository (`arthurpaivar/TBM`). It provides three commands to create, update, and remove elements (plugins, skills, commands), and ensures that every change is also reflected in the repository's main README.md and synced to the Obsidian vault.

## Skills
- **GitHub Repository Specialist**: Deep understanding of the TBM repository structure, element types (plugins, skills, commands), sync workflows between Claude/Cowork → GitHub → Obsidian, and the GitHub access method required in the Cowork VM.

## Commands
- `/create-github-element` — Create a new plugin, skill, or command in the TBM repository
- `/update-github-element` — Sync changes from Claude/Cowork to the TBM repository (primary command)
- `/remove-github-element` — Remove a plugin, skill, or command from the TBM repository (double confirmation required)

## Key Concepts
- **Repository**: `arthurpaivar/TBM` — stores plugins, skills, and commands. NOT a code repository.
- **GitHub Access**: `git clone` with token in URL is the only working method in the Cowork VM. No `gh` CLI or GitHub API.
- **Sync Direction**: Claude/Cowork → GitHub → Obsidian. Never the reverse.
- **Obsidian Structure**: Flat by type (`Plugin/`, `Skill/`, `Command/`), unlike GitHub which nests under plugin directories.

## Author
Arthur
