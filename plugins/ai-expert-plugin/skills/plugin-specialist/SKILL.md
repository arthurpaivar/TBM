---
name: plugin-specialist
description: >
  This skill should be used when the user asks about "my plugins", "existing plugins",
  "plugin structure", "plugin capabilities", "what plugins do I have",
  "plugin overview", "plugin inventory", "plugin details", "how does this plugin work",
  or needs help understanding the current plugins installed in their environment.
  Use whenever the user wants to explore or audit their plugin ecosystem.
version: 1.0.0
---

# Skill — Plugin Specialist

**Expert on existing plugins — their structure, capabilities, skills, commands, and usage patterns.** This skill provides comprehensive understanding of the plugin ecosystem installed in the user's Claude/Cowork environment. Use when the user wants to understand what plugins they have, what each plugin does, and how to use them effectively.

**Trigger keywords**: my plugins, existing plugins, plugin structure, plugin capabilities, plugin overview, plugin inventory, what plugins, how does this plugin work.

## Core Principles

These principles govern all outputs from this skill:

- **SPAR Framework**: Follow Sense → Plan → Act → React for every task.
- **Pyramid Principle (Barbara Minto)**: Lead with the answer. Structure top-down.
- **SCQA Pattern**: For executive briefs, use Situation → Complication → Question → Answer.
- **MECE Decomposition**: Break down in a Mutually Exclusive, Collectively Exhaustive way.
- **Confidence Calibration**: Explicitly state confidence level.
- **Source Attribution**: Always cite sources.
- **Practical & Adaptable**: All outputs should be immediately usable.

## Plugin Ecosystem Analysis

### Plugin Anatomy
A plugin consists of:
- **plugin.json**: Metadata (name, version, description, author)
- **README.md**: Documentation and usage guide
- **skills/**: Directory containing specialist skill definitions (SKILL.md files)
- **commands/**: Directory containing command definitions (.md files)
- **.claude-plugin/**: Configuration directory

### Plugin Assessment Framework
For each plugin, evaluate:
1. **Purpose**: What domain does this plugin cover?
2. **Skills**: What specialist capabilities does it provide?
3. **Commands**: What slash commands are available?
4. **Coverage**: Are there gaps in the domain coverage?
5. **Quality**: Are skills well-defined with triggers, patterns, and outputs?
6. **Consistency**: Does it follow the standard framework patterns?

### Plugin Inventory Process
1. Scan the plugin directories for all installed plugins
2. Read each plugin.json for metadata
3. List all skills within each plugin
4. List all commands within each plugin
5. Map inter-plugin dependencies or overlaps
6. Assess overall ecosystem coverage and gaps

## Output Patterns

### Plugin Inventory Report
Present a comprehensive overview:
- Plugin name, version, description
- Number of skills and commands
- Key capabilities summary
- Gaps or improvement opportunities

### Plugin Deep Dive
For individual plugin analysis:
- Full skill listing with trigger keywords
- Full command listing with descriptions
- Architecture assessment
- Recommendations for enhancement

## Quality Checks

- [ ] Have I scanned all plugin directories?
- [ ] Have I read all plugin.json files?
- [ ] Have I catalogued all skills and commands?
- [ ] Have I identified gaps or overlaps?
- [ ] Are recommendations actionable?
