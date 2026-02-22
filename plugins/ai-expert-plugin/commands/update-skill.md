---
description: Update an existing skill — apply changes and cascade updates to parent plugin metadata (json, README, version)
allowed-tools: Read, Write, Edit, Grep, Glob, Bash, WebSearch, WebFetch, Task
argument-hint: [skill name, parent plugin, and changes needed — e.g., "agile-specialist in technology-expert-plugin add SAFe 6.0 content"]
---

Update an existing skill for $ARGUMENTS using the skill-specialist and skill-creation-specialist skills.

## CRITICAL: Always Use Standard .plugin Packaging

**NEVER modify skill files directly in plugin installation directories.**
Even when updating a single skill, the parent plugin must be rebuilt in a temporary directory and packaged as a `.plugin` file for the user to accept through the Cowork interface.

## Layer 1 — Context & Intent

**What:** Define what skill we're updating, in which plugin, and what changes are needed.
**How:** Parse $ARGUMENTS to extract:
- Which skill is being updated?
- Which plugin does it belong to?
- What specific changes are requested? (new content, trigger keyword updates, restructuring, etc.)
- What is the expected outcome?

Clarify ambiguity with the user before proceeding. Misunderstood changes in a skill cascade to every command that invokes it.
**Why:** Updates are more sensitive than creation. This skill already works and other components depend on it. Precision of intent prevents regressions.

## Layer 2 — Knowledge Loading

**What:** Load both the skill-specialist (for reading/assessment) and skill-creation-specialist (for conventions and writing standards).
**How:** Read both SKILL.md files from this plugin. From each, extract what you need:
- From **skill-specialist**: How to read skills (Section 2), the assessment framework (Section 3), ecosystem conventions (Section 4)
- From **skill-creation-specialist**: Writing guidance (Section 3), trigger keyword engineering (Section 4), validation standards (Section 5)

You need the specialist to understand the current state, and the creation-specialist to know what "good" looks like.
**Why:** Update commands require two lenses — reading (what IS) and building (what SHOULD BE). Loading both skills gives you both.

## Layer 3 — Current State Assessment

**What:** Build a complete picture of the skill and its context as they exist right now.
**How:** Using the skill-specialist's reading and assessment methodology:
1. Read the full SKILL.md — frontmatter, introduction, every methodology section, output patterns, quality checks
2. Read the parent plugin's `plugin.json` — current description and version
3. Read the parent plugin's `README.md` — how this skill is documented
4. List all commands in the parent plugin — which ones reference this skill?
5. Map trigger keywords against all other skills in the ecosystem — any current conflicts?

Build the Skill Deep Dive output (from skill-specialist) as your baseline. You need to know exactly what exists and what depends on this skill before changing anything.
**Why:** You can't update what you don't fully understand. A skill that other commands depend on must be modified with full awareness of those dependencies.

## Layer 4 — Change Planning & Impact Analysis

**What:** Plan the specific changes and identify everything that must cascade.
**How:** For each requested change, trace its impact:

**If trigger keywords change:**
- Does the parent plugin's `plugin.json` description need updating?
- Do new triggers conflict with other skills in the ecosystem?
- Will commands that reference this skill still find it?

**If scope or methodology changes:**
- Is the skill still MECE with its siblings in the parent plugin?
- Do commands that invoke this skill need their process steps updated?
- Do output patterns still match what commands expect?

**If the skill is restructured:**
- Does the introduction still accurately describe the skill?
- Are section references in commands still valid?
- Does the README skill description still match?

**Always:**
- Parent plugin version must be bumped
- Parent plugin `plugin.json` description must be re-validated
- Parent plugin `README.md` must reflect any changes to skill name, scope, or trigger keywords

Present the change plan as a checklist before executing.
**Why:** The primary change to a skill is usually straightforward. The cascade — plugin.json, README, commands, trigger conflicts — is where updates break things. Mapping all impacts before executing prevents broken dependencies.

## Layer 5 — Execute Changes & Cascade Updates

**What:** Apply all changes — primary and cascading — rebuilding the parent plugin in a temporary directory.
**How:** Copy the current parent plugin structure to `/tmp/[plugin-name]/`, then apply changes in this order:

1. **Primary changes** — the skill modifications requested by the user
2. **Skill validation** — verify the updated skill still follows the standard SKILL.md template (frontmatter, introduction, methodology, output patterns, quality checks)
3. **Parent plugin.json updates:**
   - Bump version (minor for new capabilities, patch for improvements)
   - Update description if skill capabilities or trigger keywords changed
4. **Parent README.md updates:**
   - Update skill description if scope changed
   - Update skill-to-command mapping if references changed
5. **Command updates** — if any commands reference changed sections or output patterns, update them

Apply all changes in the temporary directory. Never modify the installed plugin directly.
**Why:** The cascade order matters. Skill first, then metadata, then documentation, then dependent commands. Each step depends on the previous being correct.

## Layer 6 — Quality Assurance Review

**What:** Verify that the updated skill and its parent plugin meet all standards before packaging.
**How:** Run through a structured validation:

**Skill Quality (from skill-creation-specialist standards):**
- Does frontmatter contain 10+ comprehensive trigger keywords?
- Is the Domain Methodology 50-60% of content and fully actionable?
- Are output patterns concrete with fillable templates?
- Are quality checks binary and domain-specific?
- Is the scope still MECE with sibling skills?

**Trigger Integrity:**
- Do updated triggers avoid conflicts with ALL other skills in the ecosystem?
- Will existing commands still find and activate this skill correctly?

**Parent Plugin Integrity:**
- Does `plugin.json` description accurately reflect all current capabilities, skill names, and command names?
- Does `README.md` accurately list all skills and commands with correct descriptions?
- Is the version bumped correctly?

**Cascade Completeness:**
- Were ALL impacted files updated (not just the SKILL.md)?
- Do all commands still reference valid skills and sections?
- Does the plugin feel coherent as a whole?

If any check fails, go back to Layer 5 and fix before proceeding. Do not package an incomplete update.
**Why:** This is the gate that prevents broken skills from reaching the user. A skill update that breaks commands or creates trigger conflicts is worse than no update at all.

## Layer 7 — Package & Deliver

**What:** Package the updated parent plugin and deliver it for user acceptance.
**How:**
```bash
cd /tmp/[plugin-name] && zip -r /tmp/[plugin-name].plugin . -x "*.DS_Store" && cp /tmp/[plugin-name].plugin [outputs-folder]/[plugin-name].plugin
```

The `.plugin` file appears in the chat as a rich preview. The user browses the files and accepts by pressing the install button. This is the ONLY method that works — even for a single skill update, the full plugin must be repackaged.
**Why:** Cowork manages its plugin cache internally. Direct file edits don't register. The full packaging flow is always required.

**Output**: An updated `.plugin` file delivered to the outputs folder, with a summary of all changes made (skill changes + cascade updates), ready for user acceptance through the Cowork interface.
