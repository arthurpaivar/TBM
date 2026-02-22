---
name: skill-specialist
description: >
  This skill should be used when the user asks about "my skills", "existing skills",
  "skill structure", "skill capabilities", "what skills do I have",
  "skill overview", "skill inventory", "how does this skill work", "skill triggers",
  "skill patterns", "skill outputs", "skill assessment", "skill quality",
  "skill ecosystem", "installed skills",
  or needs help understanding the current skills defined across their plugins.
  Also used internally by other commands that need to read and understand skill
  structure before creating or updating commands and plugins.
  Use whenever skill context is needed — whether for user queries or as a building
  block for other workflows.
version: 2.0.0
---

# Skill — Skill Specialist

**Expert on the existing skill ecosystem — structure, triggers, quality assessment, and conventions.** This skill provides the foundational knowledge for reading and understanding skills across all plugins. It serves two roles: answering user questions about their skills, and providing the skill context that other commands need when creating or updating commands and plugins.

**Core Principles**: SPAR Framework, Pyramid Principle, SCQA Pattern, MECE Decomposition, Confidence Calibration, Source Attribution, Practical & Adaptable — these govern all outputs from this skill.

**Trigger keywords**: my skills, existing skills, skill structure, skill capabilities, skill overview, skill inventory, how does this skill work, skill triggers, skill patterns, skill assessment, skill quality, skill ecosystem, installed skills.

## Section 1 — Skill Anatomy

A skill is the knowledge building block within a plugin. It holds the deep domain expertise that commands invoke. Understanding its structure is essential before assessing, extending, or modifying it.

### SKILL.md Sections and Their Roles

| Section | Purpose | What to Look For |
|---------|---------|-----------------|
| **Frontmatter** | name, description (with triggers), version | Are triggers comprehensive? Is the description discoverable? |
| **Title & Introduction** | Expert role definition, scope | Does it clearly state the persona and scope? |
| **Core Principles** | Standard reasoning principles | Present and consistent with other skills? |
| **Domain Methodology** | The deep knowledge — frameworks, processes, templates | Is it actionable or just theoretical? Is it 50-60% of content? |
| **Output Patterns** | Structured templates for deliverables | Are patterns concrete and fillable? |
| **Quality Checks** | Verification checklist | Are checks binary and domain-specific? |

### How Skills Connect to the Ecosystem

- A skill belongs to a **parent plugin** that defines the specialist domain
- Skills within a plugin must be **MECE** — each covers a distinct knowledge area, together they cover the full domain
- Each skill is invoked by one or more **commands** — if no command reaches a skill, it's an orphan
- The **trigger keywords** in the frontmatter description determine when the skill gets activated
- The model matches user intent against trigger keywords to select the right skill

### Skill Activation Mechanism

The description field in frontmatter is the activation mechanism:
1. User makes a request
2. Model scans all skill descriptions for keyword matches
3. Most relevant skill(s) are selected
4. Model loads the SKILL.md and adopts its persona and methodology

This means: **trigger keyword quality directly determines whether a skill gets used**. A skill with poor triggers is invisible.

## Section 2 — Reading Skills

### Where Skills Live

Skills are stored within their parent plugin's directory:

- **Marketplace (active)**: `/mnt/.local-plugins/marketplaces/local-desktop-app-uploads/[plugin-name]/skills/[skill-name]/SKILL.md`
- **Cache (versioned)**: `/mnt/.local-plugins/cache/local-desktop-app-uploads/[plugin-name]/[version]/skills/[skill-name]/SKILL.md`

### How to Scan Skills

**Full inventory scan:**
1. List all plugin directories in the marketplace path
2. For each plugin, list the `skills/` subdirectory to get skill names
3. Read each SKILL.md frontmatter for name, description, version
4. Extract trigger keywords from each description
5. Map triggers across all skills to identify overlaps or gaps

**Quick skill read** (when you need context on a specific skill):
1. Read the SKILL.md frontmatter for identity and triggers
2. Read the introduction for scope and persona
3. Scan section headers for methodology structure
4. Read output patterns to understand what deliverables it produces

**Cross-skill analysis** (when checking for conflicts or gaps):
1. Collect all trigger keywords across all skills in all plugins
2. Group by domain — which skills cover related areas?
3. Check for overlapping triggers (same keyword in multiple skills)
4. Check for gaps (domain areas with no skill coverage)

## Section 3 — Skill Assessment

Use this framework when evaluating a skill's current quality — whether for an audit, before an update, or as context for related work.

### Assessment Dimensions

**1. Trigger Quality**
- Does the description contain 10+ trigger keywords?
- Are all four keyword categories covered? (direct terms, synonyms, action phrases, related concepts)
- Do triggers avoid conflicts with other skills?
- Test: "If a user says [keyword], would they want THIS skill?"

**2. Domain Methodology Depth**
- Is the methodology section 50-60% of the content?
- Does it contain actionable frameworks, templates, and examples (not just descriptions)?
- Is it structured following MECE (sections don't overlap, full domain covered)?
- Could someone unfamiliar with the domain follow it and produce quality work?

**3. Scope Clarity**
- Is it clear what's IN scope vs. OUT of scope?
- Is the skill MECE with its siblings in the same plugin?
- Is the scope focused enough for genuine specialization?

**4. Output Quality**
- Are 2-4 output patterns defined?
- Are patterns concrete with fillable templates?
- Do patterns match what users actually need?

**5. Structural Compliance**
- Does it follow the standard SKILL.md template?
- Are core principles referenced?
- Are quality checks present, binary, and domain-specific?
- Does the skill name follow `[role]-specialist` convention?

### Assessment Scoring

For each dimension, assess as:
- **Strong**: Meets all criteria, production-ready
- **Adequate**: Meets most criteria, minor improvements possible
- **Weak**: Missing key elements, needs improvement
- **Missing**: Not present or fundamentally broken

## Section 4 — Ecosystem Conventions

These patterns define "good" for skills in this ecosystem. Use them as the reference when assessing or creating skills.

### Naming Conventions

| Element | Pattern | Examples |
|---------|---------|----------|
| Skill directory | `[role]-specialist` | `agile-specialist`, `plugin-creation-specialist` |
| SKILL.md name field | Same as directory name | `agile-specialist` |
| Version | Semantic: major.minor.patch | `1.0.0`, `2.0.0` |

### Description Conventions

Skill descriptions should:
- Start with `This skill should be used when the user asks about...`
- List trigger keywords explicitly in quotes
- End with the primary use case (`Use whenever...`)
- Include both user-facing triggers AND internal use cases (e.g., "Also used internally by other commands that need...")

### Structural Conventions

- **Core Principles**: One-line reference (not the full 7-principle explanation) — `SPAR Framework, Pyramid Principle, SCQA Pattern, MECE Decomposition, Confidence Calibration, Source Attribution, Practical & Adaptable`
- **Domain Methodology**: 50-60% of content, organized in numbered sections
- **Output Patterns**: 2-4 patterns with concrete templates
- **Quality Checks**: 5-9 binary checks, most critical first
- **Confidence Calibration footer**: States when confidence is high vs. medium
- **Triggers footer**: Summary sentence of when to activate

### Skill Patterns

Skills fall into archetypes that shape their methodology structure:
- **Knowledge Skill**: Organized as structured reference (frameworks, comparisons, decision trees)
- **Process Skill**: Organized as phases/steps (methodology, templates per step)
- **Communication Skill**: Organized by output type (audience calibration, tone, structure)
- **Research Skill**: Organized by methodology phase (scope, find, evaluate, synthesize)

## Section 5 — Output Patterns

### Skill Inventory
```
SKILL ECOSYSTEM: [total] skills across [total] plugins

PLUGIN: [plugin-name]
1. [skill-name] (v[version]) → [scope summary]
   Triggers: [top 5 keywords]
   Pattern: [Knowledge/Process/Communication/Research]

2. [skill-name] (v[version]) → [scope summary]
   ...

ECOSYSTEM HEALTH:
- Trigger coverage: [any gaps or overlaps]
- MECE within plugins: [assessment per plugin]
- Naming consistency: [Strong/Adequate/Weak]
```

### Skill Deep Dive
```
SKILL ASSESSMENT: [skill-name] (v[version])
Parent Plugin: [plugin-name]

IDENTITY:
- Name: [name] | Convention: [✓/✗]
- Triggers: [count] keywords | Coverage: [Strong/Adequate/Weak]
- Scope: [in-scope summary] | Boundaries: [Clear/Unclear]

METHODOLOGY:
- Depth: [% of total content] | Target: 50-60%
- Pattern: [Knowledge/Process/Communication/Research]
- Actionability: [Strong/Adequate/Weak]

ASSESSMENT:
| Dimension | Score | Notes |
|-----------|-------|-------|
| Trigger Quality | [Strong/Adequate/Weak] | [detail] |
| Methodology Depth | [Strong/Adequate/Weak] | [detail] |
| Scope Clarity | [Strong/Adequate/Weak] | [detail] |
| Output Quality | [Strong/Adequate/Weak] | [detail] |
| Structural Compliance | [Strong/Adequate/Weak] | [detail] |

RECOMMENDATIONS:
1. [Priority improvement]
2. [Secondary improvement]
```

---

**Confidence Calibration**: High confidence for individual skill assessments and inventories. Medium confidence for cross-ecosystem trigger conflict analysis on large skill sets — recommend validating findings with the user.

**Triggers**: Activate when user asks about existing skills, skill quality, or when another command needs skill context as a building block.
