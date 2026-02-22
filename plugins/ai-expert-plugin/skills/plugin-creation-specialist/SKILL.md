---
name: plugin-creation-specialist
description: >
  This skill should be used when the user asks about "create a plugin", "build a plugin",
  "new plugin", "plugin template", "how to create a plugin", "plugin design",
  "plugin authoring", "plugin development", "plugin architecture",
  "plugin scaffolding", "plugin best practices",
  or needs guidance on creating new plugins for their Claude/Cowork environment.
  Use whenever the user wants to create a new plugin from scratch.
version: 1.1.0
---

# Skill — Plugin Creation Specialist

**Expert guide for creating new plugins from scratch.** This skill provides comprehensive methodology for designing, scaffolding, and building complete plugins with skills and commands that follow the established framework patterns. Use when the user wants to create a new plugin.

**Trigger keywords**: create a plugin, build a plugin, new plugin, plugin template, how to create a plugin, plugin design, plugin authoring, plugin development, plugin architecture, plugin scaffolding.

## CRITICAL: Standard Plugin Creation Method Only

> **The ONLY reliable way to create a plugin is through the standard `.plugin` packaging method.**
>
> **NEVER** attempt to:
> - Create or edit files directly inside existing plugin directories on the file system
> - Manually edit marketplace.json or any plugin registry/metadata files
> - Copy files into `.local-plugins/` or any cache directories
> - Modify plugin files in-place on the user's machine
>
> **ALWAYS** follow this approach:
> 1. Build the complete plugin directory structure in a **temporary working directory** (e.g., `/tmp/plugin-name/`)
> 2. Package it as a `.plugin` file (zip archive)
> 3. Copy the `.plugin` file to the **outputs folder** (workspace/AI directory)
> 4. The Cowork interface will present the `.plugin` file as a rich preview card in the chat, where the user can browse the files and **accept the plugin by pressing the install button**
>
> This is the only method that works reliably. Direct file manipulation does not produce successful plugin installations because Cowork manages its plugin cache and metadata internally. Only the standard `.plugin` acceptance flow guarantees correct registration.

## Core Principles

These principles govern all outputs from this skill:

- **SPAR Framework**: Follow Sense → Plan → Act → React for every task.
- **Pyramid Principle (Barbara Minto)**: Lead with the answer. Structure top-down.
- **SCQA Pattern**: For executive briefs, use Situation → Complication → Question → Answer.
- **MECE Decomposition**: Break down in a Mutually Exclusive, Collectively Exhaustive way.
- **Confidence Calibration**: Explicitly state confidence level.
- **Source Attribution**: Always cite sources.
- **Practical & Adaptable**: All outputs should be immediately usable.

## Plugin Creation Methodology

### Phase 1: Define the Plugin (Sense)
1. **Domain**: What area of expertise does this plugin cover?
2. **Name**: Choose a descriptive kebab-case name (e.g., "finance-expert-plugin")
3. **Skills Needed**: What specialist skills should it contain?
4. **Commands Needed**: What slash commands should it expose?
5. **Overlap Check**: Does this overlap with existing plugins?

### Phase 2: Design the Architecture (Plan)
1. **Directory Structure**:
   ```
   [plugin-name]/
   ├── .claude-plugin/
   │   └── plugin.json
   ├── README.md
   ├── skills/
   │   ├── [skill-1]/
   │   │   └── SKILL.md
   │   └── [skill-2]/
   │       └── SKILL.md
   └── commands/
       ├── [command-1].md
       └── [command-2].md
   ```
2. **Skill-to-Command Mapping**: Each skill should have 1+ commands
3. **Naming Conventions**: Skills use kebab-case directories, commands use kebab-case filenames

### Phase 3: Build (Act)

> **IMPORTANT**: All files must be created in a temporary directory (e.g., `/tmp/[plugin-name]/`). Never write directly to plugin installation directories.

1. Create the full directory structure in `/tmp/[plugin-name]/`
2. Create `.claude-plugin/plugin.json` with name, version, description, author
3. Create `README.md` with overview, skills list, commands list
4. Create each `skills/[skill-name]/SKILL.md` following the standard template
5. Create each `commands/[command-name].md` following the standard template
6. **Do NOT edit marketplace.json** — the Cowork interface handles registration automatically when the user accepts the plugin

### Phase 4: Validate & Package (React)
1. **Structure Check**: All required files present in temp directory?
2. **Consistency**: Do skills and commands follow the framework?
3. **Coverage**: Are all skills accessible via commands?
4. **Triggers**: Will the right keywords activate the right skills?
5. **Documentation**: Is the README accurate and complete?
6. **Package as .plugin file**:
   ```bash
   cd /tmp/[plugin-name] && zip -r /tmp/[plugin-name].plugin . -x "*.DS_Store" && cp /tmp/[plugin-name].plugin /path/to/outputs/[plugin-name].plugin
   ```
   > Always create the zip in `/tmp/` first, then copy to the outputs folder. The `.plugin` file will appear in the chat as a rich preview where the user can browse the files and accept the plugin by pressing the install button.

## Plugin.json Template
```json
{
  "name": "[plugin-name]",
  "version": "1.0.0",
  "description": "[Plugin Name] — specialist in [domain]. Covers [key capabilities].",
  "author": {
    "name": "Arthur"
  }
}
```

## Plugin Design Patterns

### Expert Plugin Pattern
- 3-5 specialist skills covering different aspects of a domain
- 3-7 commands mapping to key user workflows
- Consistent core principles across all skills
- Output patterns aligned to deliverable types

### Naming Conventions
- Plugin: `[domain]-expert-plugin` (e.g., "finance-expert-plugin")
- Skill directory: `[role]-specialist` (e.g., "cost-analysis-specialist")
- Command file: `[action-verb].md` (e.g., "analyze-costs.md")

## Quality Checks

- [ ] Does plugin.json have correct name, version, description?
- [ ] Does README.md accurately list all skills and commands?
- [ ] Are all skills written with the standard template?
- [ ] Are all commands written with the standard template?
- [ ] Do commands correctly reference their parent skills?
- [ ] Does the directory structure follow conventions?
- [ ] Are there no orphan skills (skills without commands)?
- [ ] Is the plugin packaged as a `.plugin` file (NOT manually placed in directories)?
- [ ] Is the `.plugin` file delivered to the outputs folder for user acceptance?
