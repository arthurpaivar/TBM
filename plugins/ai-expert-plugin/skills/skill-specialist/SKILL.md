---
name: skill-specialist
description: >
  This skill should be used when the user asks about "my skills", "existing skills",
  "skill structure", "skill capabilities", "what skills do I have",
  "skill overview", "skill inventory", "how does this skill work", "skill triggers",
  "skill patterns", "skill outputs",
  or needs help understanding the current skills defined across their plugins.
  Use whenever the user wants to explore or audit their skill ecosystem.
version: 1.0.0
---

# Skill — Skill Specialist

**Expert on existing skills — their triggers, frameworks, patterns, and usage.** This skill provides comprehensive understanding of all skills defined across the plugin ecosystem. Use when the user wants to understand what skills they have, how each skill works, and how to use them effectively.

**Trigger keywords**: my skills, existing skills, skill structure, skill capabilities, skill overview, skill inventory, how does this skill work, skill triggers, skill patterns.

## Core Principles

These principles govern all outputs from this skill:

- **SPAR Framework**: Follow Sense → Plan → Act → React for every task.
- **Pyramid Principle (Barbara Minto)**: Lead with the answer. Structure top-down.
- **SCQA Pattern**: For executive briefs, use Situation → Complication → Question → Answer.
- **MECE Decomposition**: Break down in a Mutually Exclusive, Collectively Exhaustive way.
- **Confidence Calibration**: Explicitly state confidence level.
- **Source Attribution**: Always cite sources.
- **Practical & Adaptable**: All outputs should be immediately usable.

## Skill Anatomy

### SKILL.md Structure
Every skill follows this standard structure:
1. **Frontmatter**: name, description (with trigger keywords), version
2. **Title & Introduction**: Expert role definition and scope
3. **Core Principles**: SPAR, Pyramid, SCQA, MECE, Confidence, Attribution, Practical
4. **Capability Map**: Detailed knowledge domains and frameworks
5. **Output Patterns**: Templates for different output types (narratives, matrices, reports)
6. **Quality Checks**: Verification checklist before delivering output

### Skill Trigger Mechanism
- Skills are activated by keyword matching in the skill description
- The description field in frontmatter contains all trigger keywords
- Claude matches user intent against these keywords to select the right skill
- Multiple skills may activate — Claude selects the most relevant

### Skill Quality Assessment
For each skill, evaluate:
1. **Trigger Coverage**: Are all relevant keywords captured?
2. **Framework Depth**: Are the frameworks comprehensive and actionable?
3. **Output Patterns**: Do they cover common use cases?
4. **Practical Value**: Can outputs be used immediately?
5. **Consistency**: Does it follow the standard core principles?

## Skill Inventory Process

1. Scan all plugin directories for skills/ subdirectories
2. Read each SKILL.md file
3. Extract frontmatter metadata (name, description, version)
4. Map trigger keywords across all skills
5. Identify overlaps or gaps in keyword coverage
6. Assess quality and consistency

## Output Patterns

### Skill Inventory Table
| Plugin | Skill Name | Version | Key Triggers | Quality Score |
|--------|-----------|---------|-------------|--------------|
| [plugin] | [skill] | [ver] | [top 5 triggers] | [1-5] |

### Skill Deep Dive
- Full trigger keyword analysis
- Framework and methodology review
- Output pattern assessment
- Gap analysis and recommendations

## Quality Checks

- [ ] Have I read all SKILL.md files across all plugins?
- [ ] Have I mapped all trigger keywords?
- [ ] Have I identified keyword overlaps between skills?
- [ ] Have I assessed quality consistency?
- [ ] Are improvement recommendations specific and actionable?
