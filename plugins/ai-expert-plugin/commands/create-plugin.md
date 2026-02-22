---
description: Create a new plugin from scratch
allowed-tools: Read, Write, Edit, Grep, Glob, Bash, WebSearch, WebFetch, Task
argument-hint: [plugin domain and required capabilities]
---

Create a new plugin for $ARGUMENTS using the plugin-creation-specialist skill.

## CRITICAL: Always Use Standard .plugin Packaging

**NEVER create plugin files directly in plugin installation directories or edit marketplace.json manually.**
The only reliable method is to build the plugin in a temporary directory and package it as a `.plugin` file for the user to accept through the Cowork interface.

## Process

1. Load the plugin-creation-specialist skill from this plugin
2. **Discovery**: Define plugin domain, name, required skills/commands
3. **Check**: Verify no overlap with existing plugins
4. **Build in /tmp/**: Create the full directory structure in `/tmp/[plugin-name]/`:
   - `.claude-plugin/plugin.json` (manifest)
   - `README.md` (documentation)
   - `skills/[name]/SKILL.md` for each skill (standard template)
   - `commands/[name].md` for each command (standard template)
5. **Package**: Create the `.plugin` file:
   ```bash
   cd /tmp/[plugin-name] && zip -r /tmp/[plugin-name].plugin . -x "*.DS_Store" && cp /tmp/[plugin-name].plugin /path/to/outputs/[plugin-name].plugin
   ```
6. **Deliver**: The `.plugin` file appears in the chat as a rich preview. The user browses the files and accepts the plugin by pressing the install button.

**Output**: A `.plugin` file delivered to the outputs folder, ready for user acceptance through the Cowork interface.
