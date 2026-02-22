# AI Expert Plugin v2.0.0

Specialist in AI plugins, skills, commands, agents, and context windows. This plugin is the foundational tool for creating and managing the entire plugin ecosystem.

## Skills

| Skill | Purpose | Pattern |
|-------|---------|---------|
| plugin-creation-specialist | Deep methodology for creating plugins from scratch | Creation |
| plugin-specialist | Lean reference for reading and assessing existing plugins | Reference |
| skill-creation-specialist | Deep methodology for creating skills from scratch | Creation |
| skill-specialist | Lean reference for reading and assessing existing skills | Reference |
| command-creation-specialist | Deep methodology for creating commands with layered framework | Creation |
| command-specialist | Lean reference for reading and assessing existing commands | Reference |
| context-window-specialist | 6-layer architecture (L0-L5) for AI agent context windows | Creation |
| agent-creation-specialist | Methodology for building AI agents | Creation |

## Commands

| Command | Description | Skills Used |
|---------|-------------|-------------|
| /create-plugin | Create a new plugin from scratch (7 layers) | plugin-creation-specialist, plugin-specialist |
| /update-plugin | Update an existing plugin with QA gate (7 layers) | plugin-specialist, plugin-creation-specialist |
| /create-skill | Create a new skill from scratch (6 layers) | skill-creation-specialist, plugin-specialist |
| /update-skill | Update an existing skill with QA gate (7 layers) | skill-specialist, skill-creation-specialist, plugin-specialist |
| /create-commands | Create new commands for a plugin (6 layers) | command-creation-specialist, plugin-specialist, skill-specialist |
| /update-commands | Update existing commands with QA gate (7 layers) | command-specialist, command-creation-specialist, plugin-specialist |
| /create-context-window | Design a 6-layer context window for an AI agent (6 layers) | context-window-specialist |

## Architecture Principles

- **Layered Framework**: Every command uses layers with What/How/Why components
- **MECE Decomposition**: Skills within a plugin are Mutually Exclusive, Collectively Exhaustive
- **Creation + Reference pattern**: Each domain has a deep creation skill and a lean reference skill
- **QA Gate**: All update commands include a dedicated Quality Assurance layer before packaging
- **Cascade Updates**: Changes propagate through plugin.json, README, and dependent commands

## Author

Arthur
