---
description: Design and write a complete SKILL.md with domain methodology, triggers, and output patterns
allowed-tools: Read, Write, Edit, Grep, Glob, Bash, WebSearch, WebFetch, Task
argument-hint: [skill domain, parent plugin, and purpose — e.g., "agile methodology for the technology-expert-plugin"]
---

Create a new skill for $ARGUMENTS using the skill-creation-specialist skill.

## Layer 1 — Context & Intent

**What:** Define what skill we're creating, for which plugin, and why.
**How:** Parse $ARGUMENTS to extract:
- What domain does this skill cover?
- Which plugin will it belong to?
- What gap does it fill in that plugin?

Clarify ambiguity with the user before proceeding. A skill without a clear parent plugin and domain will drift in scope.
**Why:** A skill is a building block within a plugin. Its domain, scope, and boundaries are all relative to the parent plugin and its sibling skills. Without this context, you can't design a skill that fits.

## Layer 2 — Knowledge Loading

**What:** Load the skill-creation-specialist and plugin-specialist skills.
**How:** Read both SKILL.md files from this plugin. From each, extract what you need:
- From **skill-creation-specialist**: Skill Anatomy (Section 1), Design Methodology (Section 2), Writing guidance (Section 3), Trigger Keyword Engineering (Section 4), Validation Standards (Section 5), Canonical Template (Section 6)
- From **plugin-specialist**: Ecosystem Conventions (Section 4), How to Read the Ecosystem (Section 2)

Structure the extracted knowledge following MECE — separate what you need for design vs. writing vs. validation.
**Why:** The skill-creation-specialist provides the methodology for building the skill. The plugin-specialist provides the context to ensure it fits the ecosystem. Both are needed.

## Layer 3 — Parent Plugin Understanding

**What:** Read the target plugin to understand where this skill fits.
**How:** Using the plugin-specialist's reading methodology:
1. Read the parent plugin's `plugin.json` for domain and current description
2. Read all existing skills — their names, trigger keywords, scope
3. Read all existing commands — which skills they reference
4. Map the current skill-to-command architecture

Answer these questions:
- What knowledge areas are already covered by sibling skills?
- What gap does this new skill fill? (it must be MECE with siblings)
- Which existing or new commands will invoke this skill?
**Why:** A skill that overlaps with siblings creates confusion. A skill that no command reaches is an orphan. Understanding the parent plugin prevents both.

## Layer 4 — Skill Design

**What:** Design the skill before writing the SKILL.md.
**How:** Following the skill-creation-specialist's Design Methodology (Section 2):
1. Define the domain — the one-sentence test (no more than one "and")
2. Define scope boundaries — explicit IN and OUT of scope
3. Identify the skill pattern — Knowledge, Process, Communication, or Research
4. Design trigger keywords — aim for 10-15 across all four categories (direct terms, synonyms, action phrases, related concepts)
5. Plan the methodology sections — what knowledge areas to cover, in what structure
6. Define output patterns — 2-4 templates for common deliverables

Present the Skill Design Brief (from the skill-creation-specialist's output patterns) as your design artifact.
**Why:** Design-first prevents rework. The methodology structure, trigger keywords, and scope boundaries are hard to change once you start writing. Get them right here.

## Layer 5 — Content Build

**What:** Write the complete SKILL.md following the design.
**How:** Follow the section-by-section writing guidance from the skill-creation-specialist (Section 3):

1. **Frontmatter** — name, description with all trigger keywords, version (1.0.0 for new skills)
2. **Title & Introduction** — expert role definition, scope summary, core principles reference, trigger keyword list
3. **Domain Methodology** — the heart of the skill. Should be 50-60% of total content. Follow the structure determined by the skill pattern. Every section must be actionable — frameworks, templates, examples, not just descriptions
4. **Output Patterns** — 2-4 concrete templates with fillable fields
5. **Quality Checks** — 5-9 binary checks, most critical first, domain-specific
6. **Footer** — Confidence Calibration, Triggers summary

Apply MECE within the methodology sections. Apply pyramid principle in the overall structure (most important knowledge first).
**Why:** The writing order follows the anatomy. Frontmatter anchors discoverability, introduction sets the persona, methodology provides the value, output patterns standardize delivery, quality checks ensure consistency.

## Layer 6 — Quality Validation & Delivery

**What:** Verify the skill meets all standards and deliver it.
**How:** Run the full validation from the skill-creation-specialist (Section 5):

**Content Quality:**
- Does frontmatter contain 10+ comprehensive trigger keywords?
- Is the introduction clear and focused (one-sentence expert role)?
- Is the Domain Methodology 50-60% of content and fully actionable?
- Are output patterns concrete with fillable templates?
- Are quality checks binary and domain-specific?

**Ecosystem Fit:**
- Does the skill name follow `[role]-specialist` convention?
- Do triggers avoid conflicts with ALL other skills in the ecosystem?
- Is the scope MECE with sibling skills in the parent plugin?
- Will at least one command in the parent plugin invoke this skill?

**Depth Check:**
- Would this skill produce expert-level output on first use?
- Could the model follow the methodology and deliver quality work without additional context?

Write the SKILL.md to the appropriate location. Note: the parent plugin's `plugin.json` description and `README.md` will need updating to reflect the new skill — this should be done via `/update-plugin`.

**Output**: A complete SKILL.md file ready for installation in the target plugin, with a note on what parent plugin metadata needs updating.
