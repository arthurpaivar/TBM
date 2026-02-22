---
name: skill-creation-specialist
description: >
  This skill should be used when the user asks about "create a skill", "build a skill",
  "new skill", "skill template", "how to create a skill", "skill design",
  "skill authoring", "write a skill", "skill best practices", "skill framework",
  "SKILL.md template", "skill development",
  or needs guidance on creating new skills for their plugins.
  Use whenever the user wants to create or design a new skill from scratch.
version: 1.0.0
---

# Skill — Skill Creation Specialist

**Expert guide for creating new skills from scratch.** This skill provides comprehensive methodology for designing, writing, and validating new SKILL.md files that follow the established framework patterns. Use when the user wants to create a new skill for any plugin.

**Trigger keywords**: create a skill, build a skill, new skill, skill template, how to create a skill, skill design, skill authoring, write a skill, skill best practices, SKILL.md template.

## Core Principles

These principles govern all outputs from this skill:

- **SPAR Framework**: Follow Sense → Plan → Act → React for every task.
- **Pyramid Principle (Barbara Minto)**: Lead with the answer. Structure top-down.
- **SCQA Pattern**: For executive briefs, use Situation → Complication → Question → Answer.
- **MECE Decomposition**: Break down in a Mutually Exclusive, Collectively Exhaustive way.
- **Confidence Calibration**: Explicitly state confidence level.
- **Source Attribution**: Always cite sources.
- **Practical & Adaptable**: All outputs should be immediately usable.

## Skill Creation Methodology

### Phase 1: Define the Skill (Sense)
1. **Domain**: What topic or capability does this skill cover?
2. **Trigger Keywords**: What words/phrases should activate this skill?
3. **Scope**: What is in scope vs. out of scope?
4. **Users**: Who will use this skill and in what context?
5. **Overlap Check**: Does this overlap with existing skills?

### Phase 2: Design the Structure (Plan)
1. **Frontmatter**: Define name, description with triggers, version
2. **Title & Introduction**: Write expert role definition
3. **Core Principles**: Include the 7 standard principles (SPAR, Pyramid, SCQA, MECE, Confidence, Attribution, Practical)
4. **Capability Map**: Design knowledge domains, frameworks, templates
5. **Output Patterns**: Define 2-4 output formats (narratives, tables, reports, briefs)
6. **Quality Checks**: Create verification checklist

### Phase 3: Write the Content (Act)
1. Start with frontmatter — ensure trigger keywords are comprehensive
2. Write introduction that clearly defines the expert role
3. Copy the standard Core Principles section
4. Build the capability map with actionable frameworks
5. Include real-world examples and templates
6. Define output patterns with clear structure
7. Write quality checks that ensure thoroughness

### Phase 4: Validate (React)
1. **Trigger Test**: Would the right keywords activate this skill?
2. **Completeness**: Does it cover the full domain?
3. **Actionability**: Can outputs be used immediately?
4. **Consistency**: Does it match the framework pattern?
5. **Quality**: Is the content expert-level?

## SKILL.md Template

The canonical template:

### Frontmatter
- name: [kebab-case-name]
- description: > Multi-line with all trigger keywords
- version: 1.0.0

### Body Structure
1. Title: # Skill [number] — [Name]
2. Introduction paragraph (expert role, scope)
3. Trigger keywords summary
4. ## Core Principles (standard 7 principles)
5. ## [Domain] Capability Map (frameworks, methods, templates)
6. ## Output Patterns (2-4 patterns with templates)
7. ## Quality Checks (verification checklist)
8. Confidence Calibration footer
9. Triggers footer

## Trigger Keyword Best Practices

- Include the obvious terms (the thing itself)
- Include synonyms and variations
- Include action phrases ("how to X", "help with X")
- Include related concepts that imply this skill
- Avoid overly broad terms that would trigger false positives
- Test: "If a user says [keyword], would they want THIS skill?"

## Common Skill Patterns

### Knowledge Skill (e.g., AI Specialist)
- Deep domain knowledge organized as reference
- Frameworks, comparisons, decision trees
- Output: Assessments, briefs, analyses

### Process Skill (e.g., Problem-Solving Specialist)
- Step-by-step methodology
- Templates for each step
- Output: Structured deliverables (issue trees, decision matrices)

### Communication Skill (e.g., E-mail Generator)
- Audience calibration guidance
- Tone and structure templates
- Output: Ready-to-use content (emails, presentations)

### Research Skill (e.g., Deep Search Specialist)
- Source hierarchy and methodology
- Synthesis frameworks
- Output: Research reports, comparisons, trend briefs

## Quality Checks

- [ ] Does the frontmatter contain comprehensive trigger keywords?
- [ ] Does the introduction clearly define the expert role?
- [ ] Are all 7 core principles included?
- [ ] Is the capability map actionable (not just theoretical)?
- [ ] Are output patterns concrete with templates?
- [ ] Is there a quality checklist at the end?
- [ ] Would this skill produce expert-level output on first use?
- [ ] Does it avoid overlapping with existing skills?
