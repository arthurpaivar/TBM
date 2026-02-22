---
description: Create a context window for an AI agent
allowed-tools: Read, Write, Edit, Grep, Glob, Bash, WebSearch, WebFetch, Task
argument-hint: [agent purpose and domain]
---

Design and create a context window for $ARGUMENTS using the context-window-specialist skill.

Follow this process:
1. Load the context-window-specialist skill from this plugin
2. Define agent identity, role, and target users
3. Design the context architecture (identity, principles, capabilities, constraints, output patterns)
4. Allocate token budget across sections
5. Write the context window content with XML structure
6. Include guardrails, error handling, and edge case instructions
7. Validate completeness against the quality checklist

Output: Complete context window document with Identity, Core Principles, Capabilities, Constraints, Output Patterns, and Domain Knowledge sections.
