---
description: Update an existing command — apply changes and cascade updates to parent plugin metadata (json, README, version)
allowed-tools: Read, Write, Edit, Grep, Glob, Bash, WebSearch, WebFetch, Task
argument-hint: [command name, parent plugin, and changes needed — e.g., "create-skill in ai-expert-plugin add QA validation layer"]
---

Update existing commands for $ARGUMENTS using the command-specialist and command-creation-specialist skills.

## CRITICAL: Always Use Standard .plugin Packaging

**NEVER modify command files directly in plugin installation directories.**
Even when updating a single command, the parent plugin must be rebuilt in a temporary directory and packaged as a `.plugin` file for the user to accept through the Cowork interface.

## Layer 1 — Context & Intent

**What:** Define what command we're updating, in which plugin, and what changes are needed.
**How:** Parse $ARGUMENTS to extract:
- Which command is being updated?
- Which plugin does it belong to?
- What specific changes are requested? (new layers, updated frontmatter, different skill references, etc.)
- What is the expected outcome?

Clarify ambiguity with the user before proceeding. A misunderstood change in a command alters every workflow that depends on it.
**Why:** Commands are the user-facing interface. Changes to a command affect every user interaction with that workflow. Precision of intent prevents broken experiences.

## Layer 2 — Knowledge Loading

**What:** Load both the command-specialist (for reading/assessment) and command-creation-specialist (for conventions and writing standards).
**How:** Read both SKILL.md files from this plugin. From each, extract what you need:
- From **command-specialist**: How to read commands (Section 2), the assessment framework (Section 3), ecosystem conventions (Section 4)
- From **command-creation-specialist**: The layered framework pattern (Section 1), writing guidance (Section 3), validation standards (Section 4)

You need the specialist to understand the current state, and the creation-specialist to know what "good" looks like.
**Why:** Update commands require two lenses — reading (what IS) and building (what SHOULD BE). Loading both skills gives you both.

## Layer 3 — Current State Assessment

**What:** Build a complete picture of the command and its context as they exist right now.
**How:** Using the command-specialist's reading and assessment methodology:
1. Read the full command .md — frontmatter, opening instruction, constraints, every layer, output definition
2. Read the skill(s) this command references — understand what knowledge it draws from
3. Read the parent plugin's `plugin.json` — current description and version
4. Read the parent plugin's `README.md` — how this command is documented
5. Read sibling commands in the same plugin — understand the patterns they follow

Build the Command Deep Dive output (from command-specialist) as your baseline.
**Why:** You can't update what you don't fully understand. A command exists within a system of skills, plugins, and user expectations. Changing it without full context risks breaking that system.

## Layer 4 — Change Planning & Impact Analysis

**What:** Plan the specific changes and identify everything that must cascade.
**How:** For each requested change, trace its impact:

**If layers are added, removed, or restructured:**
- Does the workflow still follow a logical progression?
- Are what/how/why components present in every layer?
- Does the layer count still match the workflow complexity?

**If frontmatter changes:**
- Does the updated description still convey the outcome clearly?
- Does the argument-hint remain intuitive?
- Are allowed-tools still appropriate?
- Does the parent plugin's `plugin.json` description need updating?

**If skill references change:**
- Does the Knowledge Loading layer reference the correct skill sections?
- Does the opening instruction name the right skill(s)?
- For update commands: are both reading AND creation skills still connected?

**If output definition changes:**
- Does it still align with the referenced skill's output patterns?
- Does the `README.md` command usage examples need updating?

**Always:**
- Parent plugin version must be bumped
- Parent plugin `plugin.json` description must be re-validated
- Parent plugin `README.md` must reflect any changes to command name, description, or usage

Present the change plan as a checklist before executing.
**Why:** The primary change to a command is usually straightforward. The cascade — plugin.json, README, skill alignment — is where updates break things.

## Layer 5 — Execute Changes & Cascade Updates

**What:** Apply all changes — primary and cascading — rebuilding the parent plugin in a temporary directory.
**How:** Copy the current parent plugin structure to `/tmp/[plugin-name]/`, then apply changes in this order:

1. **Primary changes** — the command modifications requested by the user
2. **Layer validation** — verify every layer has what/how/why, layers are distinct and ordered logically
3. **Parent plugin.json updates:**
   - Bump version (minor for new capabilities, patch for improvements)
   - Update description if command names or capabilities changed
4. **Parent README.md updates:**
   - Update command description if it changed
   - Update usage examples if argument-hint or workflow changed
   - Update skill-to-command mapping if references changed
5. **Cross-reference validation** — verify all skill references are still valid, output definitions align with skill patterns

Apply all changes in the temporary directory. Never modify the installed plugin directly.
**Why:** The cascade order matters. Command first, then metadata, then documentation, then cross-references. Each step depends on the previous being correct.

## Layer 6 — Quality Assurance Review

**What:** Verify that the updated command and its parent plugin meet all standards before packaging.
**How:** Run through a structured validation:

**Command Quality (from command-creation-specialist standards):**
- Does every layer have what/how/why components?
- Is each layer a genuinely distinct stage of thinking?
- Does the Knowledge Loading layer reference specific skill sections?
- Is the frontmatter description action-oriented and under 80 characters?
- Is the argument-hint intuitive with a concrete example?

**Skill Connection Integrity:**
- Does the command reference the correct skill(s)?
- Are skill section references still valid after changes?
- For update commands: are both reading AND creation skills loaded?

**Parent Plugin Integrity:**
- Does `plugin.json` description accurately reflect all current capabilities, skill names, and command names?
- Does `README.md` accurately list all commands with correct descriptions and usage examples?
- Is the version bumped correctly?

**Cascade Completeness:**
- Were ALL impacted files updated (not just the command)?
- Does the plugin feel coherent as a whole — not like a patchwork of edits?

If any check fails, go back to Layer 5 and fix before proceeding.
**Why:** This is the gate that prevents broken commands from reaching the user. A command that references wrong skill sections or has inconsistent frontmatter erodes trust in the entire workflow.

## Layer 7 — Package & Deliver

**What:** Package the updated parent plugin and deliver it for user acceptance.
**How:**
```bash
cd /tmp/[plugin-name] && zip -r /tmp/[plugin-name].plugin . -x "*.DS_Store" && cp /tmp/[plugin-name].plugin [outputs-folder]/[plugin-name].plugin
```

The `.plugin` file appears in the chat as a rich preview. The user browses the files and accepts by pressing the install button. This is the ONLY method that works — even for a single command update, the full plugin must be repackaged.
**Why:** Cowork manages its plugin cache internally. Direct file edits don't register. The full packaging flow is always required.

**Output**: An updated `.plugin` file delivered to the outputs folder, with a summary of all changes made (command changes + cascade updates), ready for user acceptance through the Cowork interface.
