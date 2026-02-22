---
description: Design and write a layered command with what/how/why framework, connected to parent skill(s)
allowed-tools: Read, Write, Edit, Grep, Glob, Bash, WebSearch, WebFetch, Task
argument-hint: [command purpose, parent plugin, and target skill — e.g., "evaluate business cases for the finance-expert-plugin using business-case-specialist"]
---

Create new commands for $ARGUMENTS using the command-creation-specialist skill.

## Layer 1 — Context & Intent

**What:** Define what command we're creating, for which plugin, and what workflow it enables.
**How:** Parse $ARGUMENTS to extract:
- What action does this command perform for the user?
- Which plugin does it belong to?
- Which skill(s) will it invoke?
- Is this a create, update, analysis, or generation workflow?

Clarify ambiguity with the user before proceeding. A command with unclear intent produces a confused workflow.
**Why:** The command's purpose, workflow type, and skill connection determine everything — from the number of layers to the frontmatter properties to the output format.

## Layer 2 — Knowledge Loading

**What:** Load the command-creation-specialist, plugin-specialist, and skill-specialist skills.
**How:** Read the relevant SKILL.md files from this plugin. From each, extract what you need:
- From **command-creation-specialist**: Command Anatomy (Section 1), Design Methodology (Section 2), Writing Guidance (Section 3), Validation Standards (Section 4), Canonical Template (Section 5)
- From **plugin-specialist**: Ecosystem Conventions (Section 4) — to understand naming patterns
- From **skill-specialist**: Skill Anatomy (Section 1) — to understand the skill this command will invoke

Structure the extracted knowledge following MECE — separate what you need for design vs. writing vs. validation.
**Why:** The command-creation-specialist provides the layered framework methodology. The plugin-specialist provides ecosystem context. The skill-specialist helps you understand what the target skill offers so the command can reference it properly.

## Layer 3 — Parent Plugin & Target Skill Understanding

**What:** Read the target plugin and the skill(s) this command will invoke.
**How:**
1. Read the parent plugin's `plugin.json` for domain and current description
2. Read all existing commands — their names, descriptions, skill references, layer patterns
3. Read the target skill's SKILL.md — understand its sections, methodology, output patterns
4. Map the current command-to-skill architecture

Answer these questions:
- What naming patterns do existing commands follow?
- How many layers do similar commands use?
- What specific sections of the target skill should this command reference in its Knowledge Loading layer?
- What output patterns from the skill should this command's output definition align with?
**Why:** A command must fit naturally into its plugin's existing patterns. And it must connect precisely to its target skill — referencing specific sections, not just "load the skill."

## Layer 4 — Command Design

**What:** Design the command before writing the .md file.
**How:** Following the command-creation-specialist's Design Methodology (Section 2):
1. Determine the workflow type (create/update/analysis/generation)
2. Map the natural thinking stages — each becomes a candidate layer
3. Test each layer: can you clearly explain what the model thinks about at this stage? If not, merge or remove
4. Determine the layer count (don't force — let complexity dictate)
5. Design frontmatter properties:
   - description: action verb + specific outcome
   - argument-hint: intuitive with concrete example
   - allowed-tools: only what the workflow needs
6. Identify critical constraints (if any — only genuinely non-negotiable rules)

Present the Command Design Brief (from the command-creation-specialist's output patterns) as your design artifact.
**Why:** Design-first prevents rework. The layer structure, frontmatter properties, and skill connections are the architecture — getting them wrong means rewriting the entire command.

## Layer 5 — Content Build

**What:** Write the complete command .md file following the design.
**How:** Follow the writing guidance from the command-creation-specialist (Section 3):

1. **Frontmatter** — description, allowed-tools, argument-hint
2. **Opening instruction** — `[Action verb] for $ARGUMENTS using the [skill-name] skill.`
3. **Critical constraints** (if applicable) — before layers, prominently marked
4. **Each layer** — with what/how/why components:
   - Layer names: short, descriptive, convey the stage
   - What: one clear sentence stating the objective
   - How: strategic guidance with bullet points, reference specific skill sections
   - Why: one or two sentences explaining the rationale
5. **Output definition** — specific about format, content, and follow-up notes

Match the structural conventions from existing commands in the same plugin. If this is a create workflow, follow the create command pattern. If update, follow the update pattern.
**Why:** Consistency with the ecosystem matters. The model learns patterns from existing commands — a command that breaks the pattern creates confusion.

## Layer 6 — Quality Validation & Delivery

**What:** Verify the command meets all standards and deliver it.
**How:** Run the full validation from the command-creation-specialist (Section 4):

**Frontmatter Checks:**
- Description starts with action verb, under 80 characters, conveys outcome?
- Argument-hint is intuitive with concrete example?
- Allowed-tools are appropriate (not over-permissioned)?

**Layer Quality:**
- Every layer has what/how/why?
- Each layer is a genuinely distinct stage?
- Layers are ordered logically?
- Knowledge Loading references specific skill sections?
- Layer count is appropriate for complexity?

**Skill Connection:**
- Opening instruction references correct skill(s)?
- For update commands: both reading AND creation skills loaded?

**Architecture:**
- Command connects to at least one skill in the parent plugin?
- Command name follows `[action]-[object].md` convention?
- Output definition is specific?

Write the command .md to the appropriate location. Note: the parent plugin's `plugin.json` description and `README.md` will need updating to reflect the new command — this should be done via `/update-plugin`.

**Output**: A complete command .md file ready for installation in the target plugin, with a note on what parent plugin metadata needs updating.
