---
description: Design and build a complete plugin with skills and commands, packaged as .plugin for installation
allowed-tools: Read, Write, Edit, Grep, Glob, Bash, WebSearch, WebFetch, Task
argument-hint: [domain expertise and target capabilities — e.g., "finance domain covering cost analysis and budgeting"]
---

Create a new plugin for $ARGUMENTS using the plugin-creation-specialist skill.

## CRITICAL: Always Use Standard .plugin Packaging

**NEVER create plugin files directly in plugin installation directories or edit marketplace.json manually.**
The only reliable method is to build the plugin in a temporary directory and package it as a `.plugin` file for the user to accept through the Cowork interface.

## Layer 1 — Context & Intent

**What:** Define what plugin we're creating and why it matters.
**How:** Parse $ARGUMENTS to extract the domain, target users, and expected capabilities. Clarify ambiguity with the user before proceeding — a wrong intent here cascades through every layer.
**Why:** The plugin's domain and purpose determine every decision downstream — from how many skills to create, to what commands to expose, to how to name everything.

## Layer 2 — Knowledge Loading

**What:** Load the plugin-creation-specialist skill and internalize its methodology.
**How:** Read the plugin-creation-specialist SKILL.md from this plugin. Extract and structure:
- The Plugin Creation Methodology (domain decomposition, skill-to-command mapping, identity design)
- The Plugin.json Template and description best practices
- The Naming Conventions and ecosystem patterns
- The Validation Standards and quality checks

Structure this knowledge following MECE decomposition — separate what you need for design vs. build vs. validation. Apply pyramid principle — keep the templates and patterns at the top of your reasoning, the details below.
**Why:** The skill contains the accumulated best practices. Loading it properly means you work with proven patterns instead of improvising.

## Layer 3 — Ecosystem Understanding

**What:** Read the existing plugin landscape to understand patterns, conventions, and structure.
**How:** Scan all installed plugins — their plugin.json files, skill names, command names, directory structures. Don't just check for overlaps. Understand:
- How are plugins named and described?
- What's the typical skill-to-command ratio?
- What naming patterns do commands follow?
- How are descriptions written?

See the pattern in the noise. Your new plugin must feel native to this ecosystem.
**Why:** A plugin that doesn't match the ecosystem's conventions will feel foreign to the user and to the model that consumes it. Coherence matters as much as correctness.

## Layer 4 — Architecture Design

**What:** Design the complete plugin structure before writing any file.
**How:** Following Section 3 of the loaded skill, work through:
1. Define the domain (the specialist's job title test)
2. Decompose into MECE skills (each a distinct knowledge area)
3. Map skills to commands (every skill reachable, every command connected)
4. Design the plugin identity (plugin.json description with full discoverability)

Present the Plugin Blueprint (from the skill's output patterns) as your design artifact. If a skill doesn't have a clear command, or a command doesn't connect to a skill — fix it now.
**Why:** Architecture-first prevents rework. Structural problems cannot be fixed with content edits later. This is where you make the hard decisions about what the plugin contains.

## Layer 5 — Content Build

**What:** Create all plugin files following the architecture.
**How:** Build in `/tmp/[plugin-name]/` — never in plugin installation directories. Follow the build order from the loaded skill:
1. `.claude-plugin/plugin.json` — name, version (1.0.0), description (must capture domain + capabilities + skill names + command names), author
2. Each `skills/[name]/SKILL.md` — follow the standard skill template. Delegate to skill-creation-specialist for detailed methodology
3. Each `commands/[name].md` — follow the standard command template. Delegate to command-creation-specialist for detailed methodology
4. `README.md` — overview, skills list, commands list, skill-to-command mapping, usage examples

Apply the skill's frameworks within each file: SCQA for introductions, pyramid principle for structure, MECE for capability coverage.
**Why:** The build order matters — plugin.json anchors the identity, skills define the knowledge, commands expose the interface, README documents it all. Each file depends on the one before it.

## Layer 6 — Quality Validation

**What:** Verify the plugin is complete, consistent, and actionable.
**How:** Run the full validation standards from the loaded skill:
- Plugin-Level Checks: plugin.json complete, README accurate, directory correct
- Architecture Checks: skills MECE, no orphan skills, correct command-skill references, naming matches ecosystem
- Content Checks: all templates followed, trigger keywords comprehensive, no placeholders
- Packaging Checks: built in /tmp/, valid zip, delivered to outputs
**Why:** An unvalidated plugin creates technical debt. Missing triggers mean invisible capabilities. Wrong references mean broken workflows.

## Layer 7 — Packaging & Delivery

**What:** Package the plugin and deliver it to the user.
**How:**
```bash
cd /tmp/[plugin-name] && zip -r /tmp/[plugin-name].plugin . -x "*.DS_Store" && cp /tmp/[plugin-name].plugin [outputs-folder]/[plugin-name].plugin
```
The `.plugin` file appears in the chat as a rich preview. The user browses the files and accepts by pressing the install button.
**Why:** This is the ONLY method that works. Direct file manipulation doesn't produce successful plugin installations because Cowork manages its plugin cache and metadata internally.

**Output**: A `.plugin` file delivered to the outputs folder, ready for user acceptance through the Cowork interface.
