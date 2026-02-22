---
description: Update an existing plugin
allowed-tools: Read, Write, Edit, Grep, Glob, Bash, WebSearch, WebFetch, Task
argument-hint: [plugin name and changes needed]
---

Update an existing plugin for $ARGUMENTS using the plugin-creation-specialist and plugin-specialist skills.

Follow this process:
1. Load the plugin-specialist and plugin-creation-specialist skills from this plugin
2. Read the current plugin structure (plugin.json, README, skills, commands)
3. Assess current state: coverage, quality, consistency
4. Apply the requested changes (add/modify/remove skills or commands)
5. Update plugin.json version and description if needed
6. Update README.md to reflect changes
7. Validate the updated plugin follows conventions

Output: Updated plugin files with summary of changes made.
