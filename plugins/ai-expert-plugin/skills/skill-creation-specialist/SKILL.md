---
name: skill-creation-specialist
description: >
  This skill should be used when the user asks about "create a skill", "build a skill",
  "new skill", "skill template", "how to create a skill", "skill design",
  "skill authoring", "write a skill", "skill best practices", "skill framework",
  "SKILL.md template", "skill development", "design a skill", "new specialist skill",
  or needs guidance on creating new skills for their plugins.
  Use whenever the user wants to create or design a new skill from scratch.
version: 2.0.0
---

# Skill — Skill Creation Specialist

**Expert guide for creating new skills from scratch.** This skill provides the complete methodology for designing, writing, and validating SKILL.md files that follow the established ecosystem patterns. It covers domain definition, scope boundaries, section-by-section writing guidance, trigger keyword engineering, and quality validation.

A skill is the knowledge building block within a plugin. It holds the deep domain expertise that commands invoke. Creating a skill well means the model has the right knowledge to produce expert-level outputs consistently.

**Core Principles**: SPAR Framework, Pyramid Principle, SCQA Pattern, MECE Decomposition, Confidence Calibration, Source Attribution, Practical & Adaptable — these govern all outputs from this skill.

**Trigger keywords**: create a skill, build a skill, new skill, skill template, how to create a skill, skill design, skill authoring, write a skill, skill best practices, SKILL.md template, skill development, design a skill, new specialist skill.

## Section 1 — Skill Anatomy

Every SKILL.md follows a standard structure. Understanding what each section does and why it exists is essential before writing one.

### Sections and Their Roles

| Section | Purpose | Why It Matters |
|---------|---------|----------------|
| **Frontmatter** | name, description (with triggers), version | The description is how the model discovers and activates this skill. Poor triggers = invisible skill |
| **Title & Introduction** | Expert role definition, scope summary, trigger keyword list | Sets the model's persona and clarifies what this skill covers |
| **Core Principles** | SPAR, Pyramid, SCQA, MECE, Confidence, Attribution, Practical | Standard across all skills — ensures consistent reasoning quality |
| **Domain Methodology** | The deep knowledge: frameworks, processes, templates, patterns | This is the skill's unique value — the expert knowledge that commands draw from |
| **Output Patterns** | 2-4 structured templates for common deliverables | Ensures consistent, professional output formats |
| **Quality Checks** | Verification checklist before delivering | The self-review gate that catches gaps before output reaches the user |

### How Sections Connect

The skill works as a pipeline:
- **Frontmatter** gets the skill activated (triggers match user intent)
- **Introduction** sets the model's expert persona
- **Core Principles** govern how the model thinks
- **Domain Methodology** provides what the model knows
- **Output Patterns** define how the model delivers
- **Quality Checks** verify the model's work

**Key insight**: The Domain Methodology section is typically 50-60% of the skill's content. This is where the real value lives. The other sections are structural scaffolding — important but not where you should spend most of your writing effort.

## Section 2 — Skill Design Methodology

Before writing a single line of the SKILL.md, you need to design the skill. This means understanding where it fits and what it covers.

### 2.1 — Understand the Parent Plugin

A skill never exists in isolation. It belongs to a plugin, and that plugin defines the specialist domain. Before designing the skill, answer:
- What plugin will this skill belong to?
- What domain does that plugin cover?
- What other skills already exist in this plugin?
- What gap does this new skill fill?

The skill must be **MECE with its siblings** — it covers a distinct knowledge area that doesn't overlap with other skills in the same plugin, and together they cover the full domain.

### 2.2 — Define the Skill's Domain

Answer: **What specific area of expertise does this skill cover?**

A well-defined skill domain is:
- **Distinct** from other skills in the same plugin (no overlap)
- **Deep enough** to contain real methodology (frameworks, patterns, processes — not just a list of tips)
- **Focused enough** that the model can be a genuine specialist (not a generalist covering everything)

Test: Can you describe this skill's expertise in one sentence without using "and" more than once? If you need multiple "ands", the scope is too broad — split into two skills.

### 2.3 — Define Scope Boundaries

Explicitly define what's IN and OUT of scope. This prevents the skill from creeping into other skills' territory.

Example for `agile-specialist`:
- **In scope**: Scrum, Kanban, SAFe, sprint planning, retrospectives, agile metrics, user stories
- **Out of scope**: CI/CD pipelines (that's `tech-delivery-specialist`), architecture patterns (that's `architecture-specialist`)

### 2.4 — Identify the Skill Pattern

Skills fall into common archetypes. Identifying the pattern early shapes how you write the Domain Methodology section:

**Knowledge Skill** (e.g., `ai-specialist`, `architecture-specialist`)
- Organizes deep domain knowledge as structured reference
- Contains frameworks, comparisons, decision trees, concept maps
- Output: Assessments, briefs, analyses, recommendations

**Process Skill** (e.g., `problem-solving-specialist`, `plugin-creation-specialist`)
- Provides step-by-step methodology for accomplishing something
- Contains phases, templates for each step, decision points
- Output: Structured deliverables (plans, designs, implementations)

**Communication Skill** (e.g., `e-mail-generator`, `powerpoint-specialist`)
- Guides content creation for specific formats and audiences
- Contains audience calibration, tone guidance, structure templates
- Output: Ready-to-use content (emails, presentations, summaries)

**Research Skill** (e.g., `deep-search-specialist`, `industry-benchmark-specialist`)
- Provides methodology for finding, evaluating, and synthesizing information
- Contains source hierarchies, evaluation criteria, synthesis frameworks
- Output: Research reports, comparisons, trend analyses

Most skills blend patterns, but one is usually dominant. The dominant pattern determines how you structure the Domain Methodology.

## Section 3 — Writing the SKILL.md

Section-by-section guidance for writing each part well.

### 3.1 — Frontmatter

```yaml
---
name: [kebab-case-name]
description: >
  This skill should be used when the user asks about "[trigger-1]", "[trigger-2]",
  "[trigger-3]", ... or needs [primary use case description].
  Use whenever [summary of when to activate].
version: 1.0.0
---
```

The description field is the most important part of the frontmatter. See Section 4 for deep guidance on trigger keywords.

### 3.2 — Title & Introduction

```markdown
# Skill — [Name]

**[One-sentence expert role definition.]** [1-2 sentences expanding on what this skill covers, its scope, and when to use it.]

**Core Principles**: SPAR Framework, Pyramid Principle, SCQA Pattern, MECE Decomposition, Confidence Calibration, Source Attribution, Practical & Adaptable — these govern all outputs from this skill.

**Trigger keywords**: [comma-separated list matching frontmatter].
```

Best practices:
- The title should match the directory name (e.g., `agile-specialist` → `# Skill — Agile Specialist`)
- The introduction should be immediately useful — a model reading this should know exactly what persona to adopt
- Core Principles are a standard one-line reference (the model already knows them)

### 3.3 — Domain Methodology

This is the heart of the skill — 50-60% of the content. Structure depends on the skill pattern:

**For Knowledge Skills**: Organize as sections covering distinct knowledge areas. Each area should have frameworks, key concepts, and practical guidance. Use tables for comparisons, trees for decision-making.

**For Process Skills**: Organize as phases or steps. Each phase should explain WHAT to do, HOW to do it, and WHY it matters (the layered pattern we use in commands works here too). Include templates and examples.

**For Communication Skills**: Organize by output type. For each type, cover audience calibration, structure template, tone guidance, and examples.

**For Research Skills**: Organize by methodology phase (define scope, find sources, evaluate, synthesize, present). Include source hierarchies and evaluation criteria.

**Universal best practices:**
- Every section must be **actionable** — if the model reads it, can it immediately do something useful?
- Use concrete examples from the existing ecosystem where possible
- Include templates that the model can fill in, not just descriptions of what to do
- Apply MECE within the methodology — sections should not overlap and should cover the full domain

### 3.4 — Output Patterns

Define 2-4 output templates for common use cases. Each should be a concrete format the model can follow:

```markdown
## Output Patterns

### [Pattern Name]
```
[TEMPLATE HEADER]: [what goes here]

[SECTION 1]:
- [structured fields]

[SECTION 2]:
- [structured fields]
```
```

Best practices:
- Output patterns should match what users actually need (not what's theoretically complete)
- Keep templates concise — the model fills in the details
- Name patterns clearly so commands can reference them (e.g., "Plugin Blueprint", "Skill Deep Dive")

### 3.5 — Quality Checks

A checklist that the model runs before delivering output:

```markdown
## Quality Checks

- [ ] [Check 1 — most critical validation]
- [ ] [Check 2]
- [ ] ...
```

Best practices:
- 5-9 checks (fewer is too light, more is overhead)
- Order by criticality — most important first
- Each check should be binary (pass/fail) — not subjective
- Include domain-specific checks, not just generic quality

### 3.6 — Footer

```markdown
---

**Confidence Calibration**: [When confidence is high vs. medium vs. low for this domain]

**Triggers**: [When to activate this skill — summary sentence]
```

## Section 4 — Trigger Keyword Engineering

Trigger keywords determine whether the skill gets activated. A skill with poor triggers is invisible — it might as well not exist.

### Keyword Categories (aim for all four)

1. **Direct terms**: The thing itself ("agile", "scrum", "sprint")
2. **Synonyms and variations**: Alternative names ("iterative development", "agile methodology")
3. **Action phrases**: What users say when they need this ("how to run a sprint", "help with backlog")
4. **Related concepts**: Terms that imply this skill ("velocity", "story points", "retrospective")

### Writing the Description Field

The description field in frontmatter is what the model reads to match user intent. Best practices:
- Start with `This skill should be used when the user asks about...`
- List trigger keywords explicitly in quotes
- End with `Use whenever [primary use case]`
- Include 10-15 trigger keywords minimum
- Test each keyword: "If a user says [keyword], would they want THIS skill?"

### Avoiding Conflicts

- Check trigger keywords against ALL other skills in the ecosystem (not just the same plugin)
- If two skills share a trigger, make scope boundaries crystal clear in the description
- Overly broad terms (e.g., "data", "analysis") trigger false positives — qualify them (e.g., "data architecture", "cost analysis")

## Section 5 — Validation Standards

### Content Quality Checks
- [ ] Does the frontmatter contain 10+ comprehensive trigger keywords?
- [ ] Does the introduction clearly define the expert role in one sentence?
- [ ] Is the Domain Methodology actionable (contains frameworks, templates, examples — not just descriptions)?
- [ ] Is the Domain Methodology MECE (sections don't overlap, full domain covered)?
- [ ] Are output patterns concrete with fillable templates?
- [ ] Are quality checks binary (pass/fail) and domain-specific?

### Ecosystem Fit Checks
- [ ] Does the skill name follow `[role]-specialist` convention?
- [ ] Do trigger keywords avoid conflicts with other skills in the ecosystem?
- [ ] Is the scope clearly distinct from sibling skills in the same plugin?
- [ ] Does the skill connect to at least one command in the parent plugin?

### Depth Check
- [ ] Is the Domain Methodology section 50-60% of the total content?
- [ ] Would this skill produce expert-level output on first use?
- [ ] Could someone unfamiliar with the domain follow the methodology and produce quality work?

## Section 6 — Output Patterns

### SKILL.md Canonical Template

```markdown
---
name: [kebab-case-name]
description: >
  This skill should be used when the user asks about "[trigger-1]", "[trigger-2]",
  "[trigger-3]", "[trigger-4]", "[trigger-5]", ...
  or needs [primary use case description].
  Use whenever [summary of when to activate].
version: 1.0.0
---

# Skill — [Display Name]

**[One-sentence expert role definition.]** [Scope and coverage description.]

**Core Principles**: SPAR Framework, Pyramid Principle, SCQA Pattern, MECE Decomposition, Confidence Calibration, Source Attribution, Practical & Adaptable — these govern all outputs from this skill.

**Trigger keywords**: [comma-separated list].

## Section 1 — [Domain Area 1]
[Deep methodology content]

## Section 2 — [Domain Area 2]
[Deep methodology content]

## Section N — [Domain Area N]
[Deep methodology content]

## Output Patterns

### [Pattern 1 Name]
[Template]

### [Pattern 2 Name]
[Template]

## Quality Checks

- [ ] [Check 1]
- [ ] [Check 2]
- [ ] ...

---

**Confidence Calibration**: [When high vs. medium vs. low]

**Triggers**: [Activation summary]
```

### Skill Design Brief (use during planning, before writing)
```
SKILL DESIGN: [skill-name]

PARENT PLUGIN: [plugin-name]
SIBLING SKILLS: [list existing skills in same plugin]
GAP BEING FILLED: [what knowledge area this adds]

DOMAIN: [what this skill covers]
SCOPE IN: [explicit in-scope items]
SCOPE OUT: [explicit out-of-scope items]
PATTERN: [Knowledge / Process / Communication / Research]

TRIGGER KEYWORDS: [10-15 keywords across all 4 categories]

METHODOLOGY SECTIONS:
1. [Section name] → [what it covers]
2. [Section name] → [what it covers]

OUTPUT PATTERNS:
1. [Pattern name] → [when to use it]
2. [Pattern name] → [when to use it]
```

---

**Confidence Calibration**: High confidence for standard specialist skills following established patterns. Medium confidence for cross-domain skills that blend multiple patterns — recommend choosing a dominant pattern and keeping scope tight.

**Triggers**: Activate when user requests skill creation, skill design, SKILL.md writing, or needs to build a new skill from scratch.
