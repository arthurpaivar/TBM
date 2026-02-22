---
name: command-specialist
description: >
  This skill should be used when the user asks about "my commands", "existing commands",
  "slash commands", "command structure", "what commands do I have",
  "command overview", "command inventory", "how does this command work",
  "available commands", "command list",
  or needs help understanding the current commands defined across their plugins.
  Use whenever the user wants to explore or audit their command ecosystem.
version: 1.0.0
---

# Skill — Command Specialist

**Expert on existing commands — their design, execution flow, and usage patterns.** This skill provides comprehensive understanding of all commands defined across the plugin ecosystem. Use when the user wants to understand what commands they have, how each command works, and how to invoke them.

**Trigger keywords**: my commands, existing commands, slash commands, command structure, command overview, command inventory, how does this command work, available commands, command list.

## Core Principles

These principles govern all outputs from this skill:

- **SPAR Framework**: Follow Sense → Plan → Act → React for every task.
- **Pyramid Principle (Barbara Minto)**: Lead with the answer. Structure top-down.
- **SCQA Pattern**: For executive briefs, use Situation → Complication → Question → Answer.
- **MECE Decomposition**: Break down in a Mutually Exclusive, Collectively Exhaustive way.
- **Confidence Calibration**: Explicitly state confidence level.
- **Source Attribution**: Always cite sources.
- **Practical & Adaptable**: All outputs should be immediately usable.

## Command Anatomy

### Command .md Structure
Every command follows this standard structure:
1. **Frontmatter**: description, allowed-tools, argument-hint
2. **Instruction Body**: What the command does with $ARGUMENTS
3. **Process Steps**: Numbered steps for execution
4. **Skill Reference**: Which skill(s) to load
5. **Output Format**: Expected deliverable format

### Command Design Patterns
- **Single-Skill Commands**: Load one skill, apply its framework to $ARGUMENTS
- **Multi-Skill Commands**: Load multiple skills based on topic detection
- **Research Commands**: Include web search and multi-source synthesis
- **Creation Commands**: Produce files or structured outputs
- **Analysis Commands**: Evaluate inputs against frameworks

### Command Quality Assessment
For each command, evaluate:
1. **Description Clarity**: Does it clearly state what the command does?
2. **Argument Hint**: Is it clear what input the user should provide?
3. **Tool Permissions**: Are the right tools enabled?
4. **Process Steps**: Are steps logical and complete?
5. **Skill Linkage**: Does it correctly reference the parent skill?
6. **Output Definition**: Is the expected output clearly defined?

## Command Inventory Process

1. Scan all plugin directories for commands/ subdirectories
2. Read each command .md file
3. Extract frontmatter (description, allowed-tools, argument-hint)
4. Map commands to their parent skills
5. Identify gaps — skills without commands, commands without skills
6. Assess naming consistency and discoverability

## Output Patterns

### Command Inventory Table
| Plugin | Command | Description | Skill Used | Tools |
|--------|---------|------------|-----------|-------|
| [plugin] | /[cmd] | [desc] | [skill] | [tools] |

### Command Deep Dive
- Full execution flow analysis
- Skill dependency mapping
- Tool permission review
- Improvement recommendations

## Quality Checks

- [ ] Have I read all command files across all plugins?
- [ ] Have I mapped commands to their parent skills?
- [ ] Have I identified skills without commands?
- [ ] Have I assessed naming conventions?
- [ ] Are improvement recommendations actionable?
