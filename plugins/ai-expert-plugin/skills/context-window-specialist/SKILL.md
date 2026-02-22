---
name: context-window-specialist
description: >
  This skill should be used when the user asks about "context window", "system prompt",
  "agent prompt", "AI context", "prompt design", "agent instructions",
  "context optimization", "token management", "prompt engineering for agents",
  "agent persona", "agent behavior design", "system message",
  "how to create a context window", "agent configuration",
  or needs guidance on designing context windows and system prompts for AI agents.
  Use whenever the user wants to create or optimize an AI agent's context window.
version: 1.0.0
---

# Skill — Context Window Specialist

**Expert in designing context windows and system prompts for AI agents.** This skill provides comprehensive methodology for crafting effective context windows that shape agent behavior, define capabilities, set guardrails, and optimize token usage. Use when building or optimizing AI agent configurations.

**Trigger keywords**: context window, system prompt, agent prompt, AI context, prompt design, agent instructions, context optimization, token management, agent persona, agent behavior design, system message.

## Core Principles

These principles govern all outputs from this skill:

- **SPAR Framework**: Follow Sense → Plan → Act → React for every task.
- **Pyramid Principle (Barbara Minto)**: Lead with the answer. Structure top-down.
- **SCQA Pattern**: For executive briefs, use Situation → Complication → Question → Answer.
- **MECE Decomposition**: Break down in a Mutually Exclusive, Collectively Exhaustive way.
- **Confidence Calibration**: Explicitly state confidence level.
- **Source Attribution**: Always cite sources.
- **Practical & Adaptable**: All outputs should be immediately usable.

## Context Window Architecture

### Components of a Context Window
1. **Identity & Role**: Who is the agent? What is its expertise?
2. **Core Principles**: What governs the agent's behavior?
3. **Capabilities**: What can the agent do? What tools does it have?
4. **Constraints**: What should the agent NOT do?
5. **Output Patterns**: How should the agent format responses?
6. **Knowledge Base**: Domain-specific knowledge embedded in context
7. **Interaction Style**: Tone, formality, language preferences
8. **Error Handling**: How to handle uncertainty, missing info, edge cases

### Context Window Design Process

#### Phase 1: Define Agent Identity (Sense)
- What role does this agent play?
- Who are the users?
- What domain does it operate in?
- What decisions should it make vs. escalate?

#### Phase 2: Structure the Context (Plan)
- Organize information by priority (most important first)
- Group related instructions together
- Use clear section headers and XML tags for structure
- Estimate token budget and allocate to sections

#### Phase 3: Write the Content (Act)
- Start with identity and role definition
- Add core principles and behavioral guidelines
- Define capabilities and tool usage instructions
- Set constraints and guardrails
- Include output patterns with examples
- Add domain knowledge as reference material

#### Phase 4: Optimize (React)
- Test with representative queries
- Identify where the agent fails or produces poor output
- Refine instructions to address failure modes
- Optimize token usage — remove redundancy
- Iterate based on real-world usage

## Token Budget Management

### Token Allocation Strategy
- **System prompt**: 10-30% of context window
- **Conversation history**: 40-60% (varies by use case)
- **Tool definitions**: 10-20%
- **Knowledge/RAG content**: 10-30%
- **Safety buffer**: 5-10% for model output

### Optimization Techniques
- Prioritize information by frequency of use
- Use concise but clear language (avoid redundancy)
- Load knowledge dynamically (RAG) vs. static inclusion
- Use XML tags for structure (helps model parse efficiently)
- Remove low-value sections after testing

## Context Window Template

```xml
<agent_identity>
You are [Agent Name], an expert in [domain].
Your role is to [primary function].
You work with [target users] to [value proposition].
</agent_identity>

<core_principles>
- [Principle 1]: [Description]
- [Principle 2]: [Description]
- [Principle 3]: [Description]
</core_principles>

<capabilities>
You have access to the following tools:
- [Tool 1]: [When and how to use]
- [Tool 2]: [When and how to use]
</capabilities>

<constraints>
- Never [constraint 1]
- Always [constraint 2]
- When uncertain, [behavior]
</constraints>

<output_patterns>
When responding:
1. Lead with the answer (Pyramid Principle)
2. Structure: [format guidance]
3. Include: [required elements]
</output_patterns>

<domain_knowledge>
[Key reference material for the domain]
</domain_knowledge>
```

## Best Practices

### Clarity Over Brevity
- Be explicit about expected behavior
- Include examples for ambiguous cases
- Define what "good" looks like

### Defensive Design
- Anticipate edge cases and define behavior
- Include escalation paths for uncertainty
- Set clear boundaries on what NOT to do

### Testability
- Design contexts that produce consistent output
- Include verification checkpoints
- Define success criteria for key scenarios

## Quality Checks

- [ ] Does the context clearly define the agent's identity and role?
- [ ] Are core principles explicit and actionable?
- [ ] Are capabilities and tools properly documented?
- [ ] Are constraints clear and comprehensive?
- [ ] Are output patterns defined with examples?
- [ ] Is the token budget balanced appropriately?
- [ ] Has the context been tested with representative queries?
- [ ] Are edge cases and error handling addressed?
