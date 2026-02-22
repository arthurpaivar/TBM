---
name: command-specialist
description: >
  This skill should be used when the user asks about "my commands", "existing commands",
  "slash commands", "command structure", "what commands do I have",
  "command overview", "command inventory", "how does this command work",
  "available commands", "command list", "command assessment", "command quality",
  "command ecosystem", "installed commands",
  or needs help understanding the current commands defined across their plugins.
  Also used internally by other commands that need to read and understand command
  structure before creating or updating plugins and skills.
  Use whenever command context is needed — whether for user queries or as a building
  block for other workflows.
version: 2.0.0
---

# Skill — Command Specialist

**Expert on the existing command ecosystem — structure, skill connections, quality assessment, and conventions.** This skill provides the foundational knowledge for reading and understanding commands across all plugins. It serves two roles: answering user questions about their commands, and providing the command context that other workflows need when creating or updating plugins and skills.

**Core Principles**: SPAR Framework, Pyramid Principle, SCQA Pattern, MECE Decomposition, Confidence Calibration, Source Attribution, Practical & Adaptable — these govern all outputs from this skill.

**Trigger keywords**: my commands, existing commands, slash commands, command structure, command overview, command inventory, how does this command work, available commands, command list, command assessment, command quality, command ecosystem, installed commands.

## Section 1 — Command Anatomy

A command is the user-facing interface within a plugin. It's invoked as a slash command and orchestrates one or more skills to execute a workflow.

### Command .md Components

| Component | Purpose | What to Look For |
|-----------|---------|-----------------|
| **Frontmatter: description** | How the command appears in listings | Is it action-oriented and clear? Under 80 chars? |
| **Frontmatter: allowed-tools** | What tools the command can use | Are tools appropriate — not over-permissioned? |
| **Frontmatter: argument-hint** | Placeholder text for user input | Is it intuitive with a concrete example? |
| **Opening instruction** | Connects to $ARGUMENTS and declares skill(s) | Does it reference the correct skill(s)? |
| **Critical constraints** | Non-negotiable rules (when present) | Are they genuinely critical and placed before layers? |
| **Layers** | The structured thinking framework | Does each layer have what/how/why? Are they distinct stages? |
| **Output definition** | What the command delivers | Is it specific about format and content? |

### The Layered Framework Pattern

Commands follow a layered framework where each layer is a distinct stage of thinking:
- **What**: The objective for this stage
- **How**: The method (strategic guidance, not tactical micro-steps)
- **Why**: The rationale (helps prioritize and prevents skipping)

This pattern replaces the old flat numbered-step approach. Layers guide the model on *what to think about*, not *exactly what to type*.

### How Commands Connect to the Ecosystem

- A command belongs to a **parent plugin** that defines the specialist domain
- Each command invokes one or more **skills** — the skills provide the knowledge, the command orchestrates the workflow
- Commands are what **users interact with** — they're the entry point to the plugin's capabilities
- The **frontmatter properties** determine discoverability and appropriate tool access

## Section 2 — Reading Commands

### Where Commands Live

Commands are stored within their parent plugin's directory:

- **Marketplace (active)**: `/mnt/.local-plugins/marketplaces/local-desktop-app-uploads/[plugin-name]/commands/[command-name].md`
- **Cache (versioned)**: `/mnt/.local-plugins/cache/local-desktop-app-uploads/[plugin-name]/[version]/commands/[command-name].md`

### How to Scan Commands

**Full inventory scan:**
1. List all plugin directories in the marketplace path
2. For each plugin, list the `commands/` directory to get command names
3. Read each command's frontmatter for description, allowed-tools, argument-hint
4. Identify which skill(s) each command references
5. Map commands to skills across the ecosystem

**Quick command read** (when you need context on a specific command):
1. Read the frontmatter for properties
2. Read the opening instruction for skill references
3. Scan layer names for workflow structure
4. Read the output definition

**Cross-command analysis** (when checking for gaps or consistency):
1. Collect all commands grouped by parent plugin
2. Map every command to its skill(s) — identify orphan skills (skills with no command)
3. Check naming consistency across plugins
4. Compare layer patterns for similar workflow types (do all create commands follow the same pattern?)

## Section 3 — Command Assessment

Use this framework when evaluating a command's current quality.

### Assessment Dimensions

**1. Frontmatter Quality**
- Is the description action-oriented and under 80 characters?
- Is the argument-hint intuitive with a concrete example?
- Are allowed-tools appropriate (not over-permissioned, not missing needed tools)?

**2. Layer Structure**
- Does each layer have all three components (what/how/why)?
- Does each layer represent a genuinely distinct stage of thinking?
- Is the layer count appropriate for the workflow complexity?
- Are layers ordered logically (each depends on the previous)?

**3. Skill Connection**
- Does the command reference the correct skill(s)?
- For update commands: does it load both a reading AND creation skill?
- Does the Knowledge Loading layer reference specific sections from the skill?

**4. Output Clarity**
- Is the output definition specific (format, content, follow-up notes)?
- Does it match the output patterns defined in the referenced skill?

**5. Workflow Completeness**
- Does the workflow cover the full path from intent to deliverable?
- For update commands: is there a QA gate before delivery?
- For commands that modify plugins: is there a packaging/delivery layer?

### Assessment Scoring

For each dimension, assess as:
- **Strong**: Meets all criteria, production-ready
- **Adequate**: Meets most criteria, minor improvements possible
- **Weak**: Missing key elements, needs improvement
- **Missing**: Not present or fundamentally broken

## Section 4 — Ecosystem Conventions

### Naming Conventions

| Element | Pattern | Examples |
|---------|---------|----------|
| Command file | `[action]-[object].md` | `create-plugin.md`, `update-skill.md` |
| Slash command | `/[action]-[object]` | `/create-plugin`, `/evaluate-business-case` |
| Action verbs | create, update, evaluate, improve, find, list, explain | Standard verbs from existing ecosystem |

### Frontmatter Conventions

**description**: Action verb + outcome. Examples:
- `Design and build a complete plugin with skills and commands, packaged as .plugin for installation`
- `Update an existing skill — apply changes and cascade updates to parent plugin metadata`

**argument-hint**: `[key inputs — e.g., "concrete example"]`. Examples:
- `[domain expertise and target capabilities — e.g., "finance domain covering cost analysis"]`
- `[skill name, parent plugin, and changes needed — e.g., "agile-specialist add SAFe 6.0"]`

**allowed-tools**: Standard set for most commands is `Read, Write, Edit, Grep, Glob, Bash, WebSearch, WebFetch, Task`. Remove tools that aren't needed.

### Structural Conventions

- **Create commands**: 6-7 layers, single creation-specialist skill
- **Update commands**: 7 layers (with QA gate), dual skills (specialist + creation-specialist)
- **Analysis/Generation commands**: 4-5 layers, domain-specific skill
- **All commands**: Opening instruction references skill(s), output definition at end
- **Critical constraints**: Before layers, only when genuinely non-negotiable

### Layer Naming Conventions

Common layer names across the ecosystem:
- `Context & Intent` — always Layer 1
- `Knowledge Loading` — always Layer 2
- `Ecosystem Understanding` / `Parent Plugin Understanding` / `Current State Assessment` — Layer 3
- `Design` / `Change Planning & Impact Analysis` — Layer 4
- `Content Build` / `Execute Changes & Cascade` — Layer 5
- `Quality Validation` / `QA Review` — Layer 6 (or merged with delivery for simpler commands)
- `Package & Deliver` — final layer for commands that produce .plugin files

## Section 5 — Output Patterns

### Command Inventory
```
COMMAND ECOSYSTEM: [total] commands across [total] plugins

PLUGIN: [plugin-name]
1. /[command-name] → [description]
   Skill(s): [skill references]
   Layers: [count] | Type: [Create/Update/Analysis/Generation]

2. /[command-name] → [description]
   ...

ECOSYSTEM HEALTH:
- Orphan skills (no command reaches them): [list or "none"]
- Naming consistency: [Strong/Adequate/Weak]
- Layer pattern consistency: [assessment]
```

### Command Deep Dive
```
COMMAND ASSESSMENT: /[command-name]
Parent Plugin: [plugin-name]

FRONTMATTER:
- Description: [text] | Quality: [Strong/Adequate/Weak]
- Argument-hint: [text] | Intuitive: [Yes/No]
- Allowed-tools: [list] | Appropriate: [Yes/Over-permissioned/Missing tools]

WORKFLOW:
- Type: [Create/Update/Analysis/Generation]
- Layers: [count]
- Skill(s): [references]

ASSESSMENT:
| Dimension | Score | Notes |
|-----------|-------|-------|
| Frontmatter Quality | [Strong/Adequate/Weak] | [detail] |
| Layer Structure | [Strong/Adequate/Weak] | [detail] |
| Skill Connection | [Strong/Adequate/Weak] | [detail] |
| Output Clarity | [Strong/Adequate/Weak] | [detail] |
| Workflow Completeness | [Strong/Adequate/Weak] | [detail] |

RECOMMENDATIONS:
1. [Priority improvement]
2. [Secondary improvement]
```

---

**Confidence Calibration**: High confidence for individual command assessments and inventories. Medium confidence for cross-ecosystem workflow pattern analysis — recommend comparing against reference commands from the ai-expert-plugin.

**Triggers**: Activate when user asks about existing commands, command quality, or when another workflow needs command context as a building block.
