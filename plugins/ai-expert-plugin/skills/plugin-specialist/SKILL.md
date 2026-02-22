---
name: plugin-specialist
description: >
  This skill should be used when the user asks about "my plugins", "existing plugins",
  "plugin structure", "plugin capabilities", "what plugins do I have",
  "plugin overview", "plugin inventory", "plugin details", "how does this plugin work",
  "plugin architecture", "plugin assessment", "plugin ecosystem", "installed plugins",
  or needs help understanding the current plugins installed in their environment.
  Also used internally by other commands that need to read and understand plugin
  structure before creating or updating skills and commands.
  Use whenever plugin context is needed — whether for user queries or as a building
  block for other workflows.
version: 2.0.0
---

# Skill — Plugin Specialist

**Expert on the existing plugin ecosystem — structure, capabilities, conventions, and quality assessment.** This skill provides the foundational knowledge for reading and understanding plugins. It serves two roles: answering user questions about their plugins, and providing the plugin context that other commands need when creating or updating skills and commands.

**Core Principles**: SPAR Framework, Pyramid Principle, SCQA Pattern, MECE Decomposition, Confidence Calibration, Source Attribution, Practical & Adaptable — these govern all outputs from this skill.

**Trigger keywords**: my plugins, existing plugins, plugin structure, plugin capabilities, plugin overview, plugin inventory, what plugins, how does this plugin work, plugin architecture, plugin assessment, plugin ecosystem, installed plugins.

## Section 1 — Plugin Anatomy

A plugin is a self-contained specialist in a domain. Understanding its anatomy is essential before assessing, extending, or modifying it.

### Components and Their Roles

| Component | Location | Role |
|-----------|----------|------|
| `plugin.json` | `.claude-plugin/plugin.json` | **Identity** — name, version, description, author. The description is the most critical field: it drives discoverability and skill activation |
| `README.md` | Root | **Documentation** — purpose, skills list, commands list, usage examples, skill-to-command mapping |
| Skills | `skills/[name]/SKILL.md` | **Knowledge** — each skill is a distinct area of domain expertise with frameworks, patterns, and quality checks |
| Commands | `commands/[name].md` | **Interface** — each command exposes a user-facing workflow that invokes one or more skills |

### How Components Connect

The plugin works as a coherent system:
- `plugin.json` description makes the plugin **discoverable** — the model reads it to understand what the plugin can do
- Each **skill** contains deep knowledge for one area of the domain — it's a building block
- Each **command** is the user's entry point — it loads one or more skills and orchestrates a workflow
- **README.md** documents the full architecture for human understanding

**Key relationship**: Skills hold the knowledge. Commands invoke the knowledge. Every skill should be reachable through at least one command. Every command should reference at least one skill.

### Standard Directory Structure
```
[plugin-name]/
├── .claude-plugin/
│   └── plugin.json
├── README.md
├── skills/
│   ├── [skill-a]/
│   │   └── SKILL.md
│   └── [skill-b]/
│       └── SKILL.md
└── commands/
    ├── [command-1].md
    └── [command-2].md
```

## Section 2 — Reading the Ecosystem

### Where Plugins Live

Plugins are stored in the Cowork environment under two key locations:

- **Marketplace (active)**: `/mnt/.local-plugins/marketplaces/local-desktop-app-uploads/[plugin-name]/`
  This is where the currently active version of each plugin resides. Read from here for current state.

- **Cache (versioned)**: `/mnt/.local-plugins/cache/local-desktop-app-uploads/[plugin-name]/[version]/`
  This contains versioned snapshots. Useful for understanding version history.

### How to Scan the Ecosystem

**Full inventory scan:**
1. List all directories in the marketplace path to get plugin names
2. For each plugin, read `.claude-plugin/plugin.json` (or `plugin.json` at root) for identity
3. List `skills/` directory to get all skill names
4. List `commands/` directory to get all command names
5. Optionally read individual SKILL.md and command files for deeper understanding

**Quick plugin read** (when you need context on a specific plugin):
1. Read `plugin.json` for name, version, description
2. Read `README.md` for architecture overview
3. List skills and commands directories for component inventory

**Cross-plugin analysis** (when checking ecosystem coherence):
1. Collect all plugin descriptions
2. Map all skill trigger keywords across plugins
3. Identify any overlapping triggers or capability gaps
4. Assess naming convention consistency

## Section 3 — Plugin Assessment

Use this framework when evaluating a plugin's current state — whether for an audit, before an update, or as context for creating new components.

### Assessment Dimensions

**1. Identity Quality**
- Is the plugin.json description complete? Does it list capabilities, skill names, and command names?
- Does the name follow `[domain]-expert-plugin` convention?
- Is the version meaningful (incremented on changes)?

**2. Architecture Coherence**
- Is the domain decomposition into skills MECE (no overlaps, no gaps)?
- Does every skill have at least one command that reaches it? (no orphan skills)
- Does every command reference the correct parent skill(s)?
- Is the skill-to-command mapping logical from the user's perspective?

**3. Skill Quality**
- Does each SKILL.md have comprehensive trigger keywords in the frontmatter?
- Does each skill have domain-specific methodology (not just generic principles)?
- Are output patterns defined and actionable?
- Are quality checks present?

**4. Command Quality**
- Does each command have a clear, descriptive description?
- Is the argument-hint intuitive for the user?
- Does the process reference the correct skill and follow a structured approach?
- Are allowed-tools appropriate (not over-permissioned)?

**5. Documentation Quality**
- Does README.md accurately reflect the current skills and commands?
- Is the skill-to-command mapping documented?
- Are usage examples provided?

### Assessment Scoring

For each dimension, assess as:
- **Strong**: Meets all criteria, production-ready
- **Adequate**: Meets most criteria, minor improvements possible
- **Weak**: Missing key elements, needs improvement
- **Missing**: Not present or fundamentally broken

## Section 4 — Ecosystem Conventions

These are the patterns that define "good" in this ecosystem. When reading or assessing plugins, compare against these conventions.

### Naming Conventions

| Element | Pattern | Examples |
|---------|---------|----------|
| Plugin | `[domain]-expert-plugin` | `technology-expert-plugin`, `finance-expert-plugin` |
| Skill directory | `[role]-specialist` | `agile-specialist`, `plugin-creation-specialist` |
| Command file | `[action]-[object].md` | `create-plugin.md`, `evaluate-business-case.md` |
| Plugin.json name | Same as directory name | `ai-expert-plugin` |

### Description Conventions

**Plugin descriptions** should follow this pattern:
`[Plugin Name] — specialist in [domain]. Covers [capability areas]. Skills: [list]. Commands: [list].`

**Skill descriptions** should:
- List all trigger keywords explicitly
- Start with "This skill should be used when the user asks about..."
- End with the primary use case

**Command descriptions** should:
- Be concise (under 60 characters)
- Start with an action verb
- Convey the outcome, not the process

### Structural Conventions

- Typical skill-to-command ratio: each skill is reached by 1-3 commands
- Typical plugin size: 3-5 skills, 3-7 commands
- Create/update command pairs: create commands use the creation-specialist skill; update commands use both the specialist (assess) and creation-specialist (execute)
- All skills share standard Core Principles (SPAR, Pyramid, SCQA, MECE, Confidence, Attribution, Practical)

## Section 5 — Output Patterns

### Plugin Inventory
```
PLUGIN ECOSYSTEM: [total] plugins, [total] skills, [total] commands

1. [plugin-name] (v[version])
   Domain: [what it specializes in]
   Skills: [skill-1], [skill-2], [skill-3]
   Commands: /[cmd-1], /[cmd-2], /[cmd-3]

2. [plugin-name] (v[version])
   ...

ECOSYSTEM HEALTH:
- Naming consistency: [Strong/Adequate/Weak]
- Trigger coverage: [any gaps or overlaps noted]
- Architecture coherence: [orphan skills or disconnected commands]
```

### Plugin Deep Dive
```
PLUGIN ASSESSMENT: [plugin-name] (v[version])

IDENTITY:
- Name: [name] | Convention: [✓/✗]
- Description: [completeness assessment]
- Version: [version]

ARCHITECTURE:
- Skills ([count]): [list with scope summary]
- Commands ([count]): [list with skill mapping]
- Orphan skills: [none / list]
- Unmapped commands: [none / list]

ASSESSMENT:
| Dimension | Score | Notes |
|-----------|-------|-------|
| Identity | [Strong/Adequate/Weak] | [detail] |
| Architecture | [Strong/Adequate/Weak] | [detail] |
| Skill Quality | [Strong/Adequate/Weak] | [detail] |
| Command Quality | [Strong/Adequate/Weak] | [detail] |
| Documentation | [Strong/Adequate/Weak] | [detail] |

RECOMMENDATIONS:
1. [Priority improvement]
2. [Secondary improvement]
```

---

**Confidence Calibration**: High confidence for plugin inventory and individual assessments. Medium confidence for cross-ecosystem gap analysis on large plugin sets — recommend validating findings with the user.

**Triggers**: Activate when user asks about existing plugins, plugin structure, or when another command needs plugin context as a building block.
