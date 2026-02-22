---
name: command-creation-specialist
description: >
  This skill should be used when the user asks about "create a command", "build a command",
  "new command", "command template", "how to create a command", "command design",
  "slash command creation", "write a command", "command best practices",
  "command development",
  or needs guidance on creating new commands for their plugins.
  Use whenever the user wants to create a new command from scratch.
version: 1.0.0
---

# Skill — Command Creation Specialist

**Expert guide for creating new commands from scratch.** This skill provides comprehensive methodology for designing, writing, and validating command .md files that follow the established patterns. Use when the user wants to create a new slash command for any plugin.

**Trigger keywords**: create a command, build a command, new command, command template, how to create a command, command design, slash command creation, write a command, command best practices.

## Core Principles

These principles govern all outputs from this skill:

- **SPAR Framework**: Follow Sense → Plan → Act → React for every task.
- **Pyramid Principle (Barbara Minto)**: Lead with the answer. Structure top-down.
- **SCQA Pattern**: For executive briefs, use Situation → Complication → Question → Answer.
- **MECE Decomposition**: Break down in a Mutually Exclusive, Collectively Exhaustive way.
- **Confidence Calibration**: Explicitly state confidence level.
- **Source Attribution**: Always cite sources.
- **Practical & Adaptable**: All outputs should be immediately usable.

## Command Creation Methodology

### Phase 1: Define the Command (Sense)
1. **Purpose**: What does this command do?
2. **Name**: Descriptive kebab-case (e.g., "draft-email", "problem-solve")
3. **Arguments**: What input does the user provide?
4. **Parent Skill**: Which skill does this command use?
5. **Tools Needed**: Which tools does the command need access to?

### Phase 2: Design (Plan)
1. Write a clear, concise description (shown in command listing)
2. Define argument-hint (shown as placeholder text)
3. Select allowed-tools based on what the command needs
4. Design the process steps (5-7 steps)
5. Define the expected output format

### Phase 3: Write (Act)
Write the command .md file with:
1. Frontmatter: description, allowed-tools, argument-hint
2. Instruction body referencing $ARGUMENTS
3. Numbered process steps
4. Expected output format

### Phase 4: Validate (React)
1. Does the description clearly convey the command's purpose?
2. Is the argument-hint intuitive?
3. Are the right tools included?
4. Do process steps correctly reference the parent skill?
5. Is the output format aligned with the skill's output patterns?

## Command .md Template
```
---
description: [Concise description of what the command does]
allowed-tools: Read, Write, Edit, Grep, Glob, Bash, WebSearch, WebFetch, Task
argument-hint: [placeholder text for user input]
---

[Action verb] for $ARGUMENTS using the [skill-name] skill.

Follow this process:
1. Load the [skill-name] skill from this plugin
2. [Step 2]
3. [Step 3]
4. [Step 4]
5. [Step 5]
6. [Step 6]

Output: [Expected deliverable format].
```

## Tool Selection Guide

| Tool | When to Include |
|------|----------------|
| Read | Always — needed to load skills |
| Write | When creating files as output |
| Edit | When modifying existing files |
| Grep | When searching code or content |
| Glob | When finding files by pattern |
| Bash | When running CLI commands |
| WebSearch | When research is needed |
| WebFetch | When fetching web content |
| Task | When delegating to sub-agents |

## Naming Best Practices

- Use action verbs: "create-", "analyze-", "review-", "draft-"
- Keep names short but descriptive (2-3 words)
- Match the command name to the user's mental model
- Avoid abbreviations unless universally understood

## Quality Checks

- [ ] Is the description under 60 characters?
- [ ] Is the argument-hint intuitive for new users?
- [ ] Are only necessary tools included in allowed-tools?
- [ ] Do process steps correctly load and use the parent skill?
- [ ] Is the output format clear and actionable?
- [ ] Does the command name follow kebab-case convention?
