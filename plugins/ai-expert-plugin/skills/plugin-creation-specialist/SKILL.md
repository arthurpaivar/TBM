---
name: plugin-creation-specialist
description: >
  This skill should be used when the user asks about "create a plugin", "build a plugin",
  "new plugin", "plugin template", "how to create a plugin", "plugin design",
  "plugin authoring", "plugin development", "plugin architecture",
  "plugin scaffolding", "plugin best practices", "plugin structure",
  "design a plugin", "new expert plugin",
  or needs guidance on creating new plugins for their Claude/Cowork environment.
  Use whenever the user wants to create a new plugin from scratch.
version: 2.0.0
---

# Skill — Plugin Creation Specialist

**Expert guide for creating new plugins from scratch.** This skill provides the complete methodology for designing, building, and packaging plugins that follow the established ecosystem patterns. It covers domain decomposition into skills, skill-to-command mapping, plugin identity design, and the standard .plugin packaging method.

**Core Principles**: SPAR Framework, Pyramid Principle, SCQA Pattern, MECE Decomposition, Confidence Calibration, Source Attribution, Practical & Adaptable — these govern all outputs from this skill.

**Trigger keywords**: create a plugin, build a plugin, new plugin, plugin template, how to create a plugin, plugin design, plugin authoring, plugin development, plugin architecture, plugin scaffolding, design a plugin, new expert plugin.

## Section 1 — CRITICAL: Standard .plugin Packaging Only

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
> 3. Copy the `.plugin` file to the **outputs folder**
> 4. The Cowork interface will present the `.plugin` file as a rich preview card in the chat, where the user can browse the files and **accept the plugin by pressing the install button**
>
> This is the only method that works reliably. Direct file manipulation does not produce successful plugin installations because Cowork manages its plugin cache and metadata internally.

## Section 2 — Plugin Anatomy

A plugin is a self-contained specialist in a domain. It bundles knowledge (skills) and user-facing workflows (commands) into a coherent unit. Every plugin has the same physical structure:

```
[plugin-name]/
├── .claude-plugin/
│   └── plugin.json          ← Identity: name, version, description, author
├── README.md                ← Documentation: purpose, skills, commands, usage
├── skills/
│   ├── [skill-1]/
│   │   └── SKILL.md         ← Knowledge: domain expertise, frameworks, patterns
│   └── [skill-2]/
│       └── SKILL.md
└── commands/
    ├── [command-1].md        ← Action: user-facing workflow that invokes a skill
    └── [command-2].md
```

**How the pieces connect:**
- `plugin.json` defines WHAT the plugin is and makes it discoverable in the ecosystem
- Each `SKILL.md` contains the deep specialist knowledge for one area of the domain
- Each command `.md` exposes a specific workflow to the user, loading one or more skills to execute it
- `README.md` documents the full architecture for human understanding

**Existing ecosystem conventions** (scan installed plugins to confirm current patterns):
- Plugins follow `[domain]-expert-plugin` naming (e.g., `technology-expert-plugin`, `finance-expert-plugin`)
- Skills follow `[role]-specialist` naming (e.g., `agile-specialist`, `cost-analysis-specialist`)
- Commands follow `[action-verb]-[object].md` naming (e.g., `create-plugin.md`, `evaluate-business-case.md`)

## Section 3 — Plugin Design Methodology

This is the intellectual core of plugin creation. A plugin defines a specialist domain and provides the architecture where skills serve as building blocks of knowledge and commands serve as the interface to invoke them. Designing this architecture well is the hardest and most important step.

### 3.1 — Define the Domain

Start by answering: **What is this plugin a specialist in?**

A well-defined domain is:
- **Specific enough** to have clear boundaries (not "everything about technology")
- **Broad enough** to justify multiple skills (not "just one framework")
- **Coherent** — all skills within it belong to the same expertise area

Test: If you described this plugin as a person, what would their job title be? "Technology Strategy Advisor", "Financial Analyst", "Communication Expert" — if the title feels natural, the domain is right.

### 3.2 — Decompose the Domain into Skills (MECE)

Each skill represents a **distinct knowledge area** the specialist needs. The decomposition must be MECE:
- **Mutually Exclusive**: No two skills cover the same knowledge. If you find overlap, either merge them or sharpen the boundaries.
- **Collectively Exhaustive**: Together, all skills cover the full domain. If there's a gap — an expertise area that no skill addresses — add one.

**How to find the right skills:**

Ask: "What are the distinct areas of expertise this specialist needs to master?" Each answer becomes a candidate skill.

Example — `technology-expert-plugin` decomposes into:
- `agile-specialist` → Agile methodologies, Scrum, SAFe
- `architecture-specialist` → Enterprise and solution architecture patterns
- `ai-specialist` → AI, agents, LLMs, context windows
- `tech-strategy-advisory` → Digital transformation, IT strategy, roadmaps
- `tech-delivery-specialist` → SDLC, DevOps, CI/CD, release management

Each covers a distinct area. No overlap. No gaps in the technology domain.

**How many skills?** Typically 3-5. Fewer than 3 suggests the domain is too narrow for a plugin. More than 6 suggests the domain should be split into two plugins.

**Boundary test for each skill:**
- Can you clearly state what is IN scope and OUT of scope?
- If a user asks a question in this domain, is it immediately clear which skill handles it?
- Does this skill have enough depth to justify its own SKILL.md (frameworks, patterns, templates)?

### 3.3 — Map Skills to Commands

Commands are the user-facing interface — they define **what actions the user can take**. Each command invokes one or more skills to execute a workflow.

**Design principles:**
- Every skill must be reachable through at least one command (no orphan skills)
- Commands represent user workflows, not technical operations — name them from the user's perspective
- A command can invoke multiple skills when the workflow spans knowledge areas (e.g., `/update-plugin` loads both `plugin-specialist` for assessment and `plugin-creation-specialist` for execution)

**Common command patterns:**

| Pattern | Example | Skills Used |
|---------|---------|-------------|
| Create | `/create-plugin` | creation-specialist |
| Update | `/update-plugin` | specialist (assess) + creation-specialist (execute) |
| Analyze | `/evaluate-business-case` | domain-specialist |
| Generate | `/create-improve-email` | domain-specialist |

**Mapping validation:**
- Draw the map: which commands call which skills?
- Check: Is every skill called by at least one command?
- Check: Does every command have a clear parent skill?
- Check: Do commands cover the key workflows users will need?

### 3.4 — Design the Plugin Identity

The `plugin.json` is what makes the plugin visible and discoverable in the ecosystem. Its `description` field is the single most important piece of metadata — it drives skill activation and helps the model understand what the plugin can do.

**plugin.json template:**
```json
{
  "name": "[domain]-expert-plugin",
  "version": "1.0.0",
  "description": "[Plugin Name] — specialist in [domain]. Covers [list key capability areas matching skill names]. Skills: [skill-1], [skill-2], [skill-3]. Commands: /[command-1], /[command-2], /[command-3].",
  "author": {
    "name": "Arthur"
  }
}
```

**Description best practices:**
- Start with the plugin name and domain
- List the key capability areas (these should map to your skills)
- Explicitly name the skills and commands — this enables discoverability
- Keep it factual and complete — this isn't marketing, it's metadata for automation
- When in doubt, be explicit rather than concise

**README.md must document:**
- Plugin purpose and domain
- Complete skills list with descriptions of what each covers
- Complete commands list with usage examples
- The skill-to-command mapping (which commands use which skills)

## Section 4 — Build & Package

Build all files in `/tmp/[plugin-name]/`. Never write to plugin installation directories.

**Build order** (each file depends on the previous):

1. **`.claude-plugin/plugin.json`** — Anchors the identity. Name, version (1.0.0 for new plugins), description, author.

2. **Each `skills/[name]/SKILL.md`** — Write using the standard skill template. Each skill must have: frontmatter with comprehensive trigger keywords, core principles, domain-specific methodology, output patterns, quality checks. Delegate detailed skill writing to the `skill-creation-specialist` skill.

3. **Each `commands/[name].md`** — Write using the standard command template. Each command must have: frontmatter (description, allowed-tools, argument-hint), layered process referencing its parent skill, output definition. Delegate detailed command writing to the `command-creation-specialist` skill.

4. **`README.md`** — Overview, skills list, commands list, skill-to-command mapping, usage examples.

**Package and deliver:**
```bash
cd /tmp/[plugin-name] && zip -r /tmp/[plugin-name].plugin . -x "*.DS_Store" && cp /tmp/[plugin-name].plugin [outputs-folder]/[plugin-name].plugin
```

The `.plugin` file appears in the chat as a rich preview. The user browses the files and accepts by pressing the install button.

## Section 5 — Validation Standards

### Plugin-Level Checks
- [ ] Does `plugin.json` have name, version, description, and author?
- [ ] Does the description capture all capability areas, skill names, and command names?
- [ ] Does `README.md` accurately document all skills, commands, and their mapping?
- [ ] Does the directory structure follow conventions (kebab-case, correct nesting)?

### Architecture Checks
- [ ] Is the domain decomposition into skills MECE (no overlaps, no gaps)?
- [ ] Is every skill reachable via at least one command (no orphan skills)?
- [ ] Does every command reference the correct parent skill(s)?
- [ ] Do naming conventions match the ecosystem patterns?

### Content Checks
- [ ] Do all skills follow the standard SKILL.md template?
- [ ] Do all commands follow the standard command template?
- [ ] Are trigger keywords comprehensive and non-overlapping across skills?
- [ ] Is all content actionable and production-ready (no placeholders or TODOs)?

### Packaging Checks
- [ ] Was the plugin built in `/tmp/` (not in plugin installation directories)?
- [ ] Is the `.plugin` file a valid zip archive?
- [ ] Is the `.plugin` file delivered to the outputs folder?

## Section 6 — Output Patterns

### Plugin Blueprint (use during design, before build)
```
PLUGIN BLUEPRINT: [plugin-name]

DOMAIN: [What this plugin specializes in]

SKILLS (MECE decomposition):
1. [skill-name] → [What knowledge area it covers]
2. [skill-name] → [What knowledge area it covers]
3. [skill-name] → [What knowledge area it covers]

COMMANDS (User workflows):
1. /[command-name] → [What it does] → Uses: [skill-name]
2. /[command-name] → [What it does] → Uses: [skill-name]

MAPPING:
[skill-1] ← /[command-a], /[command-b]
[skill-2] ← /[command-c]
[skill-3] ← /[command-b], /[command-d]

IDENTITY:
Name: [domain]-expert-plugin
Version: 1.0.0
Description: [Full description following best practices]
```

### Delivery Confirmation
```
PLUGIN CREATED: [plugin-name]

FILES:
- .claude-plugin/plugin.json ✓
- README.md ✓
- skills/[name]/SKILL.md ✓ (× [count])
- commands/[name].md ✓ (× [count])

VALIDATION: All checks passed
PACKAGE: [plugin-name].plugin delivered to outputs folder

Next: User accepts the plugin through the Cowork interface install button.
```

---

**Confidence Calibration**: High confidence for standard expert plugin creation with 3-5 skills. Medium confidence for complex multi-domain plugins — recommend splitting into separate plugins if domain boundaries aren't clear.

**Triggers**: Activate when user requests plugin creation, plugin design, plugin scaffolding, or needs to build a new plugin from scratch.
