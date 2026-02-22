---
name: command-creation-specialist
description: >
  This skill should be used when the user asks about "create a command", "build a command",
  "new command", "command template", "how to create a command", "command design",
  "slash command creation", "write a command", "command best practices",
  "command development", "design a command", "new slash command",
  "layered command", "command framework",
  or needs guidance on creating new commands for their plugins.
  Use whenever the user wants to create a new command from scratch.
version: 2.0.0
---

# Skill — Command Creation Specialist

**Expert guide for creating new commands from scratch.** This skill provides the complete methodology for designing, writing, and validating command .md files that follow the layered framework pattern. It covers command architecture, layer design, frontmatter properties, skill connection, and the what/how/why pattern that governs all commands.

A command is the user-facing interface within a plugin. It's what users invoke as a slash command, and it orchestrates one or more skills to execute a workflow. Creating a command well means the model follows a structured thinking process and produces consistent, expert-level results.

**Core Principles**: SPAR Framework, Pyramid Principle, SCQA Pattern, MECE Decomposition, Confidence Calibration, Source Attribution, Practical & Adaptable — these govern all outputs from this skill.

**Trigger keywords**: create a command, build a command, new command, command template, how to create a command, command design, slash command creation, write a command, command best practices, command development, design a command, new slash command, layered command, command framework.

## Section 1 — Command Anatomy

Every command is a `.md` file that guides the model through a structured workflow. Understanding its components is essential before designing one.

### Components and Their Roles

| Component | Location | Role |
|-----------|----------|------|
| **Frontmatter** | YAML block at top | Properties: description, allowed-tools, argument-hint — these define how the command appears and what it can do |
| **Opening instruction** | First line after frontmatter | Connects the command to $ARGUMENTS and declares which skill(s) to load |
| **Critical constraints** | Before layers (when needed) | Non-negotiable rules that override everything (e.g., .plugin packaging requirement) |
| **Layers** | The structured body | The thinking framework — each layer guides the model through one stage of the workflow |
| **Output definition** | End of file | What the command delivers to the user |

### The Layered Framework Pattern

Commands use a **layered framework** where each layer represents a distinct stage of thinking. This is NOT a simple numbered step list. Each layer has three components:

- **What**: What the model should focus on at this stage (the objective)
- **How**: How to accomplish it (the method — big-picture guidance, not micro-instructions)
- **Why**: Why this stage matters (the rationale — helps the model prioritize and make judgment calls)

The what/how/why pattern serves a specific purpose: it tells the model *what to think about* at each stage, not *exactly what to type*. The model uses its reasoning to fill in tactical details — we guide strategic thinking.

### Command Types by Complexity

| Type | Typical Layers | Example |
|------|---------------|---------|
| **Create commands** | 6-7 layers | `/create-skill`, `/create-plugin` |
| **Update commands** | 7 layers (with QA gate) | `/update-skill`, `/update-plugin` |
| **Analysis commands** | 4-5 layers | `/evaluate-business-case` |
| **Generation commands** | 4-5 layers | `/create-improve-email` |

The number of layers depends on the workflow complexity. Never force layers — each one must earn its place by representing a genuinely distinct stage of thinking.

## Section 2 — Command Design Methodology

### 2.1 — Understand the Workflow

Before designing layers, answer:
- What does the user want to accomplish by invoking this command?
- Which skill(s) contain the knowledge needed?
- What's the logical thinking sequence from intent to deliverable?
- Are there critical constraints that must be stated upfront?

### 2.2 — Determine the Layer Count

Map the natural stages of the workflow. Common patterns:

**For create workflows (6-7 layers):**
1. Context & Intent → understand what to create
2. Knowledge Loading → load the relevant skill(s)
3. Ecosystem/Context Understanding → read the landscape to understand patterns
4. Design → plan the structure before building
5. Content Build → write the actual content
6. Quality Validation & Delivery → verify and deliver
7. Packaging (only when physical packaging is needed, e.g., .plugin files)

**For update workflows (7 layers):**
1. Context & Intent → understand what to change
2. Knowledge Loading → load reading + building skills
3. Current State Assessment → read everything as it is
4. Change Planning & Impact Analysis → trace cascading impacts
5. Execute Changes & Cascade → apply all changes
6. QA Review → gate check before delivery
7. Package & Deliver → deliver the result

**For analysis workflows (4-5 layers):**
1. Context & Intent → understand what to analyze
2. Knowledge Loading → load the domain skill
3. Data Gathering → collect the information needed
4. Analysis & Synthesis → apply frameworks, produce insights
5. Delivery → present findings

**Test**: If you can clearly explain what the model should be thinking at each layer, the layer earns its place. If two layers blur together, merge them. If one layer tries to do too much, split it.

### 2.3 — Connect to Skills

Commands orchestrate skills. The connection must be explicit:

**Single-skill commands**: Load one skill that provides all the domain knowledge.
Example: `/create-skill` loads `skill-creation-specialist`

**Dual-skill commands** (common for update workflows): Load a reading/assessment skill AND a creation/methodology skill.
Example: `/update-plugin` loads `plugin-specialist` (to read current state) + `plugin-creation-specialist` (to know conventions and packaging)

**Cross-domain commands**: Load skills from different knowledge areas.
Example: A command might load both a domain skill and the `plugin-specialist` for context.

In the Knowledge Loading layer, be explicit about WHAT to extract from each skill — reference specific sections. This prevents the model from reading the entire skill and losing focus.

### 2.4 — Design the Frontmatter Properties

Each property in the frontmatter serves a critical role for discoverability and automation:

**description** — What the command does (shown in command listings)
- Start with an action verb
- Convey the outcome, not the process
- Be specific enough that the user knows what they'll get
- Under 80 characters
- Example: `Design and write a complete SKILL.md with domain methodology, triggers, and output patterns`

**allowed-tools** — What tools the command can use
- Always include `Read` (needed to load skills)
- Include `Write` when creating files
- Include `Edit` when modifying files
- Include `Bash` when CLI operations are needed (e.g., packaging)
- Include `WebSearch, WebFetch` when research is part of the workflow
- Include `Task` when the command may need to delegate complex subtasks
- Don't over-permission: only include tools the workflow genuinely needs

**argument-hint** — Placeholder text shown to the user
- Must be intuitive — a new user should understand what to type
- Include a concrete example in the hint
- Example: `[skill domain, parent plugin, and purpose — e.g., "agile methodology for the technology-expert-plugin"]`

## Section 3 — Writing the Command

### 3.1 — File Structure

```markdown
---
description: [Action-oriented description of the outcome]
allowed-tools: [comma-separated tool list]
argument-hint: [intuitive placeholder with example]
---

[Action verb] for $ARGUMENTS using the [skill-name] skill.

## CRITICAL: [Constraint Name] (only if applicable)

[Non-negotiable constraint that overrides everything]

## Layer 1 — [Layer Name]

**What:** [Objective — what the model focuses on]
**How:** [Method — big-picture guidance, not micro-steps]
**Why:** [Rationale — why this stage matters]

## Layer 2 — [Layer Name]
...

## Layer N — [Layer Name]
...

**Output**: [What the command delivers to the user]
```

### 3.2 — Writing Effective Layers

**Layer names** should be short, descriptive, and convey the stage (e.g., "Context & Intent", "Knowledge Loading", "Ecosystem Understanding", "QA Review")

**What section**: One clear sentence stating the objective. Don't explain HOW — that's the next section.

**How section**: Guide the strategic thinking, not the tactical execution. Tell the model what to consider, what to extract, what questions to answer. Use bullet points for multiple considerations. Reference specific skill sections when loading knowledge.

**Why section**: One or two sentences explaining the rationale. This helps the model prioritize when making judgment calls. It also prevents skipping this layer under token pressure.

### 3.3 — Critical Constraints

Some commands have non-negotiable rules that must be stated before the layers. These go in a prominently marked section:

```markdown
## CRITICAL: [Constraint Name]

**NEVER [prohibited action].**
[Explanation of the only correct approach.]
```

Use only when there's a genuine constraint that, if violated, breaks the workflow entirely (e.g., the .plugin packaging requirement). Don't overuse — if everything is critical, nothing is.

### 3.4 — Output Definition

End the command with a clear output statement:

```markdown
**Output**: [What the user receives — file type, format, content, and any follow-up notes]
```

Be specific: "A complete SKILL.md file" is better than "The skill file". Include notes about cascading actions if relevant (e.g., "the parent plugin's plugin.json will need updating").

## Section 4 — Validation Standards

### Frontmatter Checks
- [ ] Does the description start with an action verb and convey the outcome?
- [ ] Is the description under 80 characters?
- [ ] Is the argument-hint intuitive with a concrete example?
- [ ] Are allowed-tools limited to what the workflow genuinely needs?

### Layer Quality Checks
- [ ] Does each layer have all three components (what/how/why)?
- [ ] Does each layer represent a genuinely distinct stage of thinking?
- [ ] Are layers ordered logically (each depends on the previous)?
- [ ] Does the Knowledge Loading layer reference specific skill sections?
- [ ] Is the layer count appropriate for the complexity (not forced)?

### Skill Connection Checks
- [ ] Does the opening instruction name the correct skill(s)?
- [ ] Are skill references in layers pointing to the right sections?
- [ ] For update commands: are both the reading AND creation skills loaded?

### Architecture Checks
- [ ] Does the command connect to at least one skill in the parent plugin?
- [ ] Does the command name follow `[action]-[object].md` convention?
- [ ] Is there a clear output definition at the end?
- [ ] If critical constraints exist, are they before the layers?

## Section 5 — Output Patterns

### Command .md Canonical Template (Create Workflow)

```markdown
---
description: [Action-oriented outcome description]
allowed-tools: Read, Write, Edit, Grep, Glob, Bash, WebSearch, WebFetch, Task
argument-hint: [intuitive placeholder — e.g., "domain and purpose"]
---

[Action verb] for $ARGUMENTS using the [skill-name] skill.

## Layer 1 — Context & Intent

**What:** Define what we're creating and why.
**How:** Parse $ARGUMENTS to extract [key elements]. Clarify ambiguity before proceeding.
**Why:** [Why intent matters for this workflow.]

## Layer 2 — Knowledge Loading

**What:** Load the [skill-name] skill and internalize its methodology.
**How:** Read the [skill-name] SKILL.md. Extract:
- [Specific section/knowledge to extract]
- [Specific section/knowledge to extract]
**Why:** The skill contains the accumulated best practices.

## Layer 3 — [Context/Ecosystem Understanding]

**What:** [Read the landscape]
**How:** [How to scan and understand context]
**Why:** [Why context matters]

## Layer 4 — [Design]

**What:** [Design before building]
**How:** [Design methodology]
**Why:** [Why design-first matters]

## Layer 5 — Content Build

**What:** [Write the actual content]
**How:** [Build order and guidance]
**Why:** [Why this order matters]

## Layer 6 — Quality Validation & Delivery

**What:** [Verify and deliver]
**How:** [Quality checks to run]
**Why:** [Why validation matters]

**Output**: [What is delivered to the user]
```

### Command Design Brief (use during planning)
```
COMMAND DESIGN: /[command-name]

PARENT PLUGIN: [plugin-name]
SKILL(S) USED: [skill-1], [skill-2]
WORKFLOW TYPE: [Create / Update / Analysis / Generation]

FRONTMATTER:
- description: [draft]
- argument-hint: [draft]
- allowed-tools: [list]

LAYERS:
1. [Layer name] → [what model thinks about]
2. [Layer name] → [what model thinks about]
...

OUTPUT: [what user receives]
```

---

**Confidence Calibration**: High confidence for standard create/update commands following established patterns. Medium confidence for novel workflow types — recommend starting with a close existing command as reference and adapting.

**Triggers**: Activate when user requests command creation, command design, slash command writing, or needs to build a new command from scratch.
