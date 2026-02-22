---
description: Update an existing skill
allowed-tools: Read, Write, Edit, Grep, Glob, Bash, WebSearch, WebFetch, Task
argument-hint: [skill name and changes needed]
---

Update an existing skill for $ARGUMENTS using the skill-creation-specialist and skill-specialist skills.

Follow this process:
1. Load the skill-specialist and skill-creation-specialist skills from this plugin
2. Read the current SKILL.md file
3. Assess current quality: trigger coverage, framework depth, output patterns
4. Apply the requested changes while maintaining framework consistency
5. Validate that the updated skill follows the standard template
6. Ensure no trigger keyword conflicts with other skills

Output: Updated SKILL.md file with summary of changes made.
