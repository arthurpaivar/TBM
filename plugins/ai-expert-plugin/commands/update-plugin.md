---
description: Update an existing plugin — apply changes and cascade updates to all dependent files (json, README, version), packaged as .plugin for installation
allowed-tools: Read, Write, Edit, Grep, Glob, Bash, WebSearch, WebFetch, Task
argument-hint: [plugin name and changes needed — e.g., "ai-expert-plugin update the plugin-specialist skill"]
---

Update an existing plugin for $ARGUMENTS using the plugin-specialist and plugin-creation-specialist skills.

## CRITICAL: Always Use Standard .plugin Packaging

**NEVER modify plugin files directly in plugin installation directories or edit marketplace.json manually.**
The only reliable method is to rebuild the plugin in a temporary directory and package it as a `.plugin` file for the user to accept through the Cowork interface. This applies even for small changes — there is no "quick edit" path.

## Layer 1 — Context & Intent

**What:** Define what we're updating and why.
**How:** Parse $ARGUMENTS to extract:
- Which plugin is being updated?
- What specific changes are requested? (new skill, modified command, updated description, etc.)
- What is the expected outcome?

Clarify ambiguity with the user before proceeding. A misunderstood intent means wasted work — and with updates, it can also mean breaking existing functionality.
**Why:** Updates are more sensitive than creation. You're modifying something that already works. Precision of intent prevents regressions.

## Layer 2 — Knowledge Loading

**What:** Load both the plugin-specialist (for reading/assessment) and plugin-creation-specialist (for conventions and packaging).
**How:** Read both SKILL.md files from this plugin. From each, extract what you need:
- From **plugin-specialist**: How to read the ecosystem (Section 2), the assessment framework (Section 3), ecosystem conventions (Section 4)
- From **plugin-creation-specialist**: Plugin identity best practices (Section 3.4), validation standards (Section 5), packaging method (Section 4)

You need the specialist to understand the current state, and the creation-specialist to know what "good" looks like and how to package the result.
**Why:** Update commands require two lenses — reading (what IS) and building (what SHOULD BE). Loading both skills gives you both.

## Layer 3 — Current State Assessment

**What:** Build a complete picture of the plugin as it exists right now.
**How:** Using the plugin-specialist's reading methodology:
1. Read `plugin.json` — current name, version, description
2. Read `README.md` — current documentation
3. List and read all skills — their names, trigger keywords, scope
4. List and read all commands — their descriptions, argument-hints, skill references
5. Map the current architecture: which commands call which skills

Build the Plugin Deep Dive output (from plugin-specialist) as your baseline. You need to know exactly what exists before changing anything.
**Why:** You can't update what you don't fully understand. Missing a dependency here means breaking it in Layer 5. This layer is your safety net.

## Layer 4 — Change Planning & Impact Analysis

**What:** Plan the specific changes and identify everything that must cascade.
**How:** For each requested change, trace its impact across the plugin:

**If a skill is added or modified:**
- Does `plugin.json` description need updating to reflect new capabilities?
- Does `README.md` skills list need updating?
- Do any commands need updating to reference the new/changed skill?
- Do trigger keywords conflict with other skills in the ecosystem?

**If a command is added or modified:**
- Does `README.md` commands list need updating?
- Does `plugin.json` description need updating to list the new command?
- Is the referenced skill still correct?

**If a skill or command is removed:**
- Are there orphan skills (skills with no command reaching them)?
- Are there broken commands (commands referencing removed skills)?
- Does `README.md` still reflect reality?

**Always:**
- Version must be bumped (increment minor for additions, patch for fixes)
- `plugin.json` description must be re-validated against current capabilities
- `README.md` must match the actual skills and commands

Present the change plan as a checklist before executing.
**Why:** This is the intellectual core of the update command. The primary change is usually straightforward — it's the cascade that gets missed. Mapping all impacts before executing prevents broken plugins.

## Layer 5 — Execute Changes & Cascade Updates

**What:** Apply all changes — primary and cascading — rebuilding the plugin in a temporary directory.
**How:** Copy the current plugin structure to `/tmp/[plugin-name]/`, then apply changes in this order:

1. **Primary changes** — the skill/command modifications requested by the user
2. **plugin.json updates:**
   - Bump version (minor for new capabilities, patch for improvements)
   - Update description to reflect current capabilities, skill names, and command names
3. **README.md updates:**
   - Update skills list if skills changed
   - Update commands list if commands changed
   - Update skill-to-command mapping if architecture changed
   - Update usage examples if relevant
4. **Cross-reference validation** — verify all commands still reference valid skills, all skills still have commands reaching them

Apply all changes in the temporary directory. Never modify the installed plugin directly.
**Why:** The cascade order matters. Primary changes first, then metadata, then documentation, then validation. Each step depends on the previous being correct.

## Layer 6 — Quality Assurance Review

**What:** Verify that the updated plugin meets all framework standards before packaging.
**How:** Run through a structured Q&A validation against the full set of standards:

**Identity & Metadata:**
- Does `plugin.json` have name, version (bumped), description (complete with all skill names and command names), and author?
- Does the description follow the convention: `[Name] — specialist in [domain]. Covers [areas]. Skills: [list]. Commands: [list].`?
- Is the version increment correct (minor for additions, patch for improvements)?

**Architecture & Coherence:**
- Is the domain decomposition into skills still MECE after the changes?
- Are there orphan skills (no command reaches them)?
- Are there broken commands (referencing skills that don't exist or changed names)?
- Does the skill-to-command mapping still make logical sense?

**Content Quality:**
- Do all skills follow the standard SKILL.md template (frontmatter, trigger keywords, core principles, methodology, output patterns, quality checks)?
- Do all commands follow the layered framework pattern (description, argument-hint, allowed-tools, layers with what/how/why)?
- Are trigger keywords comprehensive and non-overlapping across skills?
- Is all content actionable and production-ready (no placeholders or TODOs)?

**Documentation Accuracy:**
- Does `README.md` accurately list ALL current skills with descriptions?
- Does `README.md` accurately list ALL current commands with usage examples?
- Is the skill-to-command mapping documented and correct?

**Cascade Completeness:**
- Were ALL impacted files updated (not just the primary change)?
- Does the plugin feel coherent as a whole — not like a patchwork of edits?

If any check fails, go back to Layer 5 and fix before proceeding. Do not package an incomplete update.
**Why:** This is the gate that prevents broken plugins from reaching the user. Every standard we've established — MECE skills, layered commands, complete metadata, accurate documentation — must be verified here. Shipping a plugin that fails these checks erodes trust in the entire ecosystem.

## Layer 7 — Package & Deliver

**What:** Package the updated plugin and deliver it for user acceptance.
**How:**
```bash
cd /tmp/[plugin-name] && zip -r /tmp/[plugin-name].plugin . -x "*.DS_Store" && cp /tmp/[plugin-name].plugin [outputs-folder]/[plugin-name].plugin
```

The `.plugin` file appears in the chat as a rich preview. The user browses the files and accepts by pressing the install button. This is the ONLY method that works — Cowork manages its plugin cache internally, direct file edits don't register.
**Why:** Even for "small" updates, the full packaging flow is required. No exceptions.

**Output**: An updated `.plugin` file delivered to the outputs folder, with a summary of all changes made (primary and cascading), ready for user acceptance through the Cowork interface.
